# Multiplayer

## blocks plan
- [x] add whatever block metadata is needed to nodes
- [x] redis streams to sync updates to a node to all listeners
- [x] on update to a node the listeners receive the new node
- [x] attach avatar state to the collapsible wrapper
- [x] when you update you change the version and you cannot update without being on the latest version
- [x] sync publish state
- [x] attach avatar state also to the editor
- [x] check every node
- [ ] simple fix for update race condition is like... check if this current session is making the edits then don't overwrite the local.?

## for fun..
- tiptap -> mdx..
- fix task / run streaming
- clean up like... the use editor state stuff
- add alert on url spikes to datadog
- remove intercom
- add react query debugger
- replace toast with sonner and add buttons

## rushlight plan
- consolidate state into string
  - write node <> directive mapping
  - make a functional version of each editor and bring it in
  - external editors might also be depending on this string
- multiplayer the string rushlight style w/ redis and lexical state...

## plan for single mdx editor
After reflection This might work, but we still need to support many other nodes. Unless we want to converge all nodes into this one single node, we might as well just implement node- or block-level multiplayer.

* bring state into the mdx - into the each node
  - minimal version is putting it into the node key
  - better version is having some kind of delimiting such that it's not a pita to read
* state comes from step node
* you only edit the step node
* for now we edit the actual node row in the db when the step node node gets edited
* need a nonce on the node to know if you need to update
* the mdx node value is just the json of the zod schema
* then........ you can just YJS or rushlight the whole document

## constraints
* few users.... simple doc

## random
* compaction?
* ot vs crdt


## prompts

I want to build my own custom container based markdown directive that lets me embed arbitrary json data into these directives

For example, a normal container directive might look like this
<markdown>
# some title

::: tip
this is some tip
:::

Some more text
</markdown>

What I want to build is a more advanced version that looks like this

<markdown>
# some title

::: node
{
  "name": "someName",
  "nestedObject": { "A": "X", "B": [1, 2, 3] },
  "arrayOfSomeKind": [1, 2, 3],
  "anythingReally": true
}
:::

This is some more text
</markdown>

Given some directive like this, I want to be able to edit this with a custom React component. I want to define many different kinds of nodes, each with their own data type and each with their own React component. This React component could really be anything. It could be input sliders, text areas, buttons, whatever I want really. It should just be arbitrary React. And the interesting thing is I want to create some kind of binding where as I use these inputs, they edit the directive content underneath.  So for example, you can imagine me having a radio button to set the `anythingReally` variable above to `true` or `false`.

I also don't want the React components to know about MDX, Markdown, or MDAST.   I want them to just take in some value and a callback to edit that value. Then, some shared container component would serialize that incoming value and update the MDAST. So you can see there's this one bridge component and many many possible react editor components.

Consider the code here: apps/frontend/src/pages/Flows/Editor/components/flow-doc-editor/node-directive-descriptor.tsx
I have the beginnings of this directive here... Can you write a proof of concept of this feature with clean concise code and we can go from there. This POC should include all the features I've described above and two simple example child editor components that edit slightly different jsons. The child components should have some buttons, inputs, and a radio.