# TODO

- [ ] Give quick overview on all the use cases that customers are using Pace for

---

# Week of Feb 22 - March 1

# Week of Feb 16 - 22

Refactor order for sandbox...

- create task (incorporate with router
- snapshot tracking
- remove "Sandbox" prefix from as many things as possible lol

Made a backup of the computer use stuff here - yogi/add-sandbox-computeruse-tool-backup

# Week of Feb 9 - 13

Tasks:

- [x] Clean up manifest
- [ ] Based on clean manifest, ensure that certain tool configs are persisted as REST API call configs. Agent can run code to call this API
- [ ] Write a new send email tool that the agent can use to send an email that respects allow lists.
- [ ] Plan for MCP

- [ ] Send email tool / capability -- For communications, send email etc; Do we do fake MCP
- [ ] REST API tool - For rest api tool maybe we put the tool config into a file that then the agent can refer to and do stuff with. Is this not just a skill for that specific rest api call?
- [ ] Add export skill (Ryze and WTW) - Ryze wants to create PDF with rule results and WTW wants to modify a template Excel file with some data and then send it in an email or something.. Probably upload
- [ ] Disambiguate between readonly and write ableskills
- [ ] Fix bad skills route? (mb rachel is doing this)
- [ ] Publish button to publish a new version of the agent
- [ ] Can batch how long the agent runs before its stopped and a new activity is spun up
- [ ] Agents can pick up from where they crashed/were paused or stopped. (scheduled to different activity etc.)

## Friday Feb 13 2026

### 📄 voice-cua-v3-demo.md (Last modified: 2026-02-20)

# Demo

- [ ] See sub agents handling incoming requests in this sandbox
- [ ] Be speaking to it on a live call
- [ ] Kick off cua instances

# Tactically

- Kick off plans, work on coat of paint
- [ ] Task tool call
- [ ] Coat of paint that seems nice
- [ ] Task tool with generic sub agent instructions
- [ ] Voice integration (L)
- [ ] CUA integration (M) ( just a tool call )

---

## Thursday Feb 12 2026

- working on yogi/implement-sandbox-email-tooling-stub for send email functionality
- rest api functionality with extract seems to work

// TODO

// move all the manifest stuff into a folder
// rename run - streams to streams
// all the run\* stuff should be specific to flow runs, every thing else should have a more generic name

## Wednesday Feb 11 2026

- [o] Main agent doesn't make manual extraction files - Might be because agent wasn't waiting

## Tuesday Feb 10 2026

### 📄 THOUGHTS.md (Last modified: 2026-02-10)

I say this not to spread fud or fearmonger or ask for an answer but -- the world is changing fast and I think we need to adapt. The question here is how can we become a generational company that's a beloved fixture of the insurance and financial services apparatus. We need to deliver significant value to customers and sustainably capture it.

---

- Spent a bunch of time getting entities over the line, PR just kept ballooning. I'm not sure what to do about it.
  It seems like all the PRs end up so fat. There's a lot of refactoring...

## Monday Feb 9 2026

### 📄 extraction-agent.md (Last modified: 2026-02-09)

# Extraction agent

## Customer requests for extraction

### Smaller requests

- Ability to perform simple calculations
- Good summaries of documents that are too large to fit in context window
- Ability to exclude certain pages documents under certain conditions
  - Can we enforce this or is it up to the LLM's judgment?
- Ability to handle Excel docs

### Bigger milestones

- Can we completely or partially drop Reducto/Textract?
  - Currently being used for chunking and bounding boxes for citations
  - Costs a lot
  - Run into a lot of issues with reliability and accuracy (missed checkboxes or form fields, etc.)
- Can we self improve? A large chunk of FDE time can end up being prompt engineering
  - What would the ideal system look like? Architecture, cadence of running, etc.
  - What is a good UX for this?
- What is the ideal pipeline
  - Can we make this a lot faster and cheaper?

- [ ] Simple extractions
- [ ] Using code to do transformations/calculations
- [ ] Can use vision to find more information
- [ ] Can convert various files to markdown or similar
- [ ] Can handle navigating an excel spreadsheet

---

---

# Week of Feb 2 - 6

Promises:

- [x] Editor with AOP
- [ ] Ryze flow - level capabilities
  - [x] Upload multiple emails in create task
  - [x] Extractions
  - [ ] Rules
  - [ ] Export
- [ ] Editor with versioning

Tasks:

- [ ] Add export skill.
- [ ] Disagbiguate between readonly and write ableskills
- [ ] Fix bad skills
- [ ] Publish button to publish a new version of the agent
- [ ] Can batch how long the agent runs before its stopped and a new activity is spun up
- [ ] Agents can pick up from where they crashed/were paused or stopped. (scheduled to different activity etc.)

## Friday Feb 6 2026

- [x] Actually plumb email from the attachment into the sandbox
- [x] Add attachments to the create task email
- [x] Show extraction nodes in the main editor
- [x] Migrate button to migrate nodes to files
- [x] Show the nodes even if its not in the files api response.
- [x] Show rule nodes in the main editor
- [x] Implement a pure agent version of extractions, Rules while waiting
- [x] Sub agents actually work

## Wednesday Feb 4 2026

### 📄 sandbox-agents.md (Last modified: 2026-02-04)

# TODO

High level

Ryze flow

- [ ] Intake email
- [ ] Extractions
- [ ] Rules
- [ ] Export

TMG flow -- all ryze stuff except export with

- [ ] Running code
- [ ] REST Api
- [ ] Can we run code to call tools?

## Smaller rocks

- [ ] Agent will load its own messages on load with an agent id by inspecting ndjson
- [ ] The "Should stop" agent functionality should be determined by if it just called the done tool instead of the stop requested stuff
- [ ] Clean up the NJSON log
- [ ] Clean up stream events so they are cleaner
- [ ] Verify that this snapshotting works across versions. bring back publish
- [ ] Do auto save on file edit
- [ ] Sidebar that's more simplified and doesn't literally show a file system. It should also have data model definitions
- [ ] How would voice being alive be handled? Does the main agent sleep until voice is done?

## Big rocks

- [ ] Sub agents for stuff like extraction / cua / voice
- [ ] Persistence for longer running agents. Can we actually just add a new set of DBs and then we can also make sure we add a row to task and run and we'll get the data there.
- [ ] Figure out how to integrate with reporting. Maybe this will just be based on results.......

## Done

- [x] We need tool preambles from the agent. Now that I think about it I think the reasoning is missing completely. It is now showing separately.
- [x] Figure out how to eval the Openai requests. Specifically just skills as UAR is python...
- [x] RFC for the agent migration
- [x] Optimized for working with Openai -- Luis is handling
  - [x] Testing excel spreadsheet skills
  - [x] Testing misc. skills
  - [x] Having a better understanding of the sandbox environment

---

- Lauren onsite, help onboard

## Tuesday Feb 3 2026

- [ ] Create task with multiple PDFs

- [ ] Plan for extractions and rules
  - [ ] Show the nodes in the file system
  - [ ] At least make the agent aware of being able to extract from those
  - [ ] Spin up N sub agents, one per each field
  - [ ] Add all the data to a result.ndjson file so each agent can just write to it atomically
  - [ ] Same thing for rules

- [ ] Plan for Export
  - [ ] Would it be a skill? An export skill that we can make available to the agent? Maybe it comes with scripts that can take in this information

# Friday Jan 30 2026

- [ ] Push the flow run steps thing
- [ ] Store the full request response trace so that agents that get interrupted can pick back up. Store logs with an agent id that temporal provides and on startup we can look for those logs.
- [ ] Change the extract tool such that it ends right after you kick off all the subagents and then the subagents are just responsible for writing to the result file -- need to find a way to do this atomically so there are no race conditions....
- [ ] try beautiful mermaid for diagrams..

Interesting idea from kim just convert all the old flows/tasks into a huge json file that the agent can then represent. Might work. Need some way to sync between results and s3

# Thursday Jan 29 2026

Need some way to deep dive and visualize a specific sub agents trace

## OAI Feedback

- The skill doesn't actually get used? It's unclear what gets the skill to get used.
- general strat for getting data out of unstructured
- Can we make a deterministic skill? Like if a skill requires 3 API calls in sequence, we have some guarantee that it actually gets called? Would we have the skill call a script in that case?
- For the UAR here's what we need
  - snapshot
  - restore
  - clone
  - excel
  - manifest is cool

# Wednesday Jan 28 2026

OAI Feedback

- Skills are interesting but we're not going to use the container or the loading of skills. We have data requirements that we have to comply with
-

# Tuesday Jan 27 2026

- [ ] Merge the flow run steps update
      We launched the sequoia fundraise today
- Added notes today in /sandbox-agents.md

# Clean up old tasks

- [N] Devin style "Browser" / "Voice call" tab design
- [x] Wrap up diffing
- [x] Research conversational agent
- [x] Think about general agent harness and how we can make it more usable and self serve....
- [x] Shared set of entities for child agents instead of cloned entities

# Monday Jan 26 2026

# Friday Jan 23 2026

### 📄 search-agent-plan.md (Last modified: 2026-01-23)

# Search agent

## Goals

1. validate that a generic search agent could work

- canopius wants to search over a bunch of tasks to look for similar tasks
- we want to embed things

2. replace COR with agentic search

- validate it by running it against different things -- compare cost vs regular synthesis somehow....

3. See if we can make a more general backbone that we can use for all our agents....

## Tasks

- [x] Clean up orchestrate single extraction (remove all the patches)
- [x] Find a way to handle vision -- basically just answer synthesis as a tool..???
- [ ] Excel functionality
- [ ] Embed documents as part of ingestion
- [ ] Run it on prod against actual extractions
- [ ] Figure out the ID aliasing thing. Do we want the UUIDs to be so prevalent?
- [ ] Generic agent interface that we can plug different pieces of tools into and it will search whatever

- [ ] Fix various eval failures
  - [ ] Error: "consider every single chunk" type use case. Rule looking for spelling issues, the search agent is not optimized for that
        {
        "correctionId": null,
        "createdAt": "2026-01-05T23:36:43.69Z",
        "entryKey": "c434e361-2ec6-4e60-b830-b0e283e92036:result",
        "fieldPath": "result",
        "flowId": "04c6b895-abdb-48de-85f7-fdf833751f88",
        "flowVersionId": "3218cc25-0d0f-4541-8569-a4370d76c36f",
        "nodeId": "a4466144-c23e-472b-9669-2b4cdd6517b4",
        "orgId": "bd5edef8-af19-45c2-a795-d043c6e4bc85",
        "resultId": "c434e361-2ec6-4e60-b830-b0e283e92036",
        "runId": "1e92830b-e0cc-4ec6-9be9-1581cabc4729",
        "taskId": "1887acb6-6a75-468e-b497-a7bc7be068cf",
        "taskUrl": "https://app.withpace.com/tasks/1887acb6-6a75-468e-b497-a7bc7be068cf"
        }

- [ ] Error: Thinks question 6 is blank but its not
      https://www.braintrust.dev/app/Foundation/p/Search%20Agent/experiments/search-agent-eval-1769101802738?c=search-agent-eval-1769011675851&r=216fb4e4-49f5-4642-bc79-156e574131b7&s=216fb4e4-49f5-4642-bc79-156e574131b7
      {
      "correctionId": null,
      "createdAt": "2026-01-05T22:31:12.332Z",
      "entryKey": "8889398f-4bd9-4a3b-9e2a-4da089669b04:result",
      "fieldPath": "result",
      "flowId": "04c6b895-abdb-48de-85f7-fdf833751f88",
      "flowVersionId": "3218cc25-0d0f-4541-8569-a4370d76c36f",
      "nodeId": "c9511c2b-87d2-4893-8620-39fefeb378dd",
      "orgId": "bd5edef8-af19-45c2-a795-d043c6e4bc85",
      "resultId": "8889398f-4bd9-4a3b-9e2a-4da089669b04",
      "runId": "57ce7669-3e87-4896-ae1d-a105737cc384",
      "taskId": "17bb0567-8e00-49f6-9bca-1506d11f9fa9",
      "taskUrl": "https://app.withpace.com/tasks/17bb0567-8e00-49f6-9bca-1506d11f9fa9"
      }

## Customers

### WTW

- 16k row excel, want to extract like 5 rows out of the file
- 3 sheets in the larger spreadsheet
- this needs to get put into an extraction result
- spreadsheet coming in as an email attachment
- IDEAL: show monday morning that this works

### Realign

- same thing
- IDEAL: ready for jan 26

### Novacore

- Handle SOP with 100+ API requests that need to be done. Obviously none of them can be dropped

---

My general priorities

- Remain high leverage, make sure the team is on the bleeding edge
- Remain involved in the building of the company - stay T shaped

We need to let this thing write code. That's this year's version of leaning into non-determinism.
So many of the issues I've seen over the last week are all just -- the agent can't write code.

- My number 1 priority today:
  - See if embedding everything is feasible
  - Shadow search agent in production
  - See if it can run code to extract excel

# Thursday Jan 22 2026

- Some debugging stuff
- [x] Vision capabilities are in

# Wednesday Jan 21 2026

## Priorities

- Things I should want to focus on
  - Making sure we're on the bleeding edge
  - Getting leverage across the engineering org
- Things I'm thinking about dropping
  - Design / positioning

My 1 year anniversary at Pace

Agent runtimes

- Modal vs e2b vs daytona. e2b seems more easily self hosted and has BYOC on aws. Modal is a cooler startup
- I'd like to do a file system type project where we satisfy the same agent interface but ideally its faster and runs on a file system and can run code and use skills and whatnot
- I'd also like to do this for rules and extractions. What's a good way to satisfy these constraints ? I need entities, run steps, and results uploaded to the db so the rest of the app like reporting and corrections can work.

Projects

- Need agentic excel extraction support for demo on Jan 26 - can improve capabilities
- Need to deliver big "rewrite" ASAP - can set us up for the future and make things more reliable, code first, setup for the future.
  - Interesting overview https://chatgpt.com/c/696e95c0-ac1c-832b-a3dc-0cbd60fb7f1e
  - things that are foundational
    - files
    - writing and running code
    - API / integrations / mcp / connectors
  - things that are "tricks to get better performance"
    - skills
    - very specific tool calls (ex: send email tool call)
    - abstractions like entities / results / whatever

  we should cut down on tricks and build on foundations

# Tuesday Jan 20 2026

- Did some misc. stuff

# Monday Jan 19 2026

- Working on search agent. Need to do a better job keeping track of what I was doing last time so I can pick back up.
- Need to approve designs for the solutions page -- seems fine

# Friday Jan 16 2026

- set up weekly meeting for core agent last week
- working on search agent evals expansion and better types
- what if we rewrote the agent....... to be based on a file system.

# Wednesday Jan 14 2026

Company goal

- I think the main company goal is to be on the edge of development
- We must be automating all work as much as we can
- Our feature velocity must be disgustingly high

Deloitte
contextual reasoning engine

- repeated tasks

- Which llms do you use
- How is the agent framework
  - our goal is to construct a world for our agents to operate in and give it the right tools so that in any different environment it can perform well
- Partnership with openai, anthropic to fine tune models for certain cases
- agents out of the box

Notes for Andy

- Hey Andy we're ready to kick off a rebrand + new site exercise
- High level what does your availability look like? We're aiming to finish this by end of Q1 if possible
- We'd like to do a brand adjustment. Last time we talked a lot of the branding was around replacing paper or document heavy work and you'll see that a lot of our brand elements match that, but we'd like to
  orient more broadly towards being: "The AI partner for insurance companies".

- full branding would add 3 to 4 weeks to this
- would be able to start early feb

# Tuesday Jan 13 2026

- [x] Follow up with Kim on the designer stuff

# Monday Jan 12 2026

- [x] Can we get started on agentic search actually

- Rob video notes

Thanks! It's really coming together

[0:14-0:20] I don't think its clear that these instructions are what the agent is following in the next section at [0:20-0:31]. Some rough notes/ideas

- Can we unify this to look more like the next section? Ideally what the user types here directly becomes the agent instructions and then the agent starts following them.
- It doesn't feel like the Pace editor. I think it should be clearer that the user is working in the Pace app to make these instructions.
- It feels a bit disjointed to go from what the user writes to the slightly different set of instructions for the "FNOL AI Agent".

[0:35] Could we make these more visually distinct? Ex: they have SMS, Excel, etc. instead of all being the same screen
[0:45] Extra / incomplete screen?
Can we tie the agents at [0:37] more clearly to the task screen at [0:39]? We also need to give it a refresh IMO it looks disjointed from the other visual elements. Assuming the plan is also to unify it with the screen at the beginning?

- Music is better!

Some more misc. ennui
Had a conversation with E on what's worth working on. Seems like he's generally pretty bored.

# Friday Jan 9 2026

- [x] Small routing change

# Thursday Jan 8 2026

- [x] Fix the race condition issue where the second text quickly needs to get reminded
- [x] Fix issue where we can re-awaken workflow correctly
  - [x] figure out how we prevent re-awakening flows that actually shouldn't be re-awoken
- [x] Verify conversational agent routing bug fixes, then that message routing works.
- [x] Check that pricing usage went down for CMV
- [ ] Verify gpt-realtime transcription
- [o] Don't break cache on nonce change
- [ ] Use LLM pass on tasker feedback to identiy issues with component gathering
- [ ] Actually remove the checkbox path

# Wednesday Jan 7 2026 (!!)

Thanks! Some feedback

- The dropdown pops up weirdly when we switch pages (see video)
- Testimonial needs logo and link to blog post
- A lot of the text feels a bit small and a bit disjoint from the other pages. We can make the copy shorter if that helps?

Hey just catching up on everything. My current priorities -- does this line up?

- Conversational agents
  - Message routing
  - Transcription improvements
- Agents out of the box
  - Working w/ Kim on brainstorming / coding as helpful
- Launch
  - Solutions page w/ David
  - Video w/ Rob
- Agentic search
- Misc eng work

One flag: Rob hasn't sent an updated video he said he would send Monday - real chance of missing launch deadline here I think. Since he seems to respond better to pings from you could you give him a quick bump? Parts of the website are downstream of this so very important

Given a generic SOP wouldn't claude code be able to actually execute on it right now?

- [x] Feedback to David Kalman about website
  - [x] rec video about dropdown
- [x] Check that pricing usage went down for CMV
- [ ] Verify gpt-realtime transcription
- [o] Don't break cache on nonce change
- [ ] Use LLM pass on tasker feedback to identiy issues with component gathering
- [ ] Actually remove the checkbox path

What we're here to do is take people and turn them into agents. What we have absolute respect for is the data.

# Friday Jan 2 2025

### 📄 transcription.md (Last modified: 2026-01-02)

# Transcription

- Wisprflow is clearly good why is this bad?
  - wisprflow fine tuned llama https://www.baseten.co/resources/customers/wispr-flow/
- can we stalk someone's info based on their phone

Notes from Bharat:

- llm pass
- focus on the prompting - there's a lot to be gained just from focusing the thing on collecting the info in the correct way
- give it reasonable words
- clean up pass on the transcription based on common knowledge
- look up addresses on google, verify phone numbers, etc.
- call ppl with diff voice models and then see how it does

---

- [x] Respond to comments on search agent
- [x] Attempt a pass on transcription errors

# Tuesday Dec 30 2025

- [x] Video feedback for Rob
- [x] Merge vision

# Monday Dec 29 2025

There's some long tail of stuff but remember the goal grid. Let us keep that in mind.

## Must do first

- [x] Ryze before EOY - image rules
- [x] Doc for search agent

# Tuesday Dec 23 2025

-

# Friday Dec 19 2025

### 📄 diff-view.md (Last modified: 2025-12-19)

- See text diff view like Github
  - prefers github view
- collapse nodes

---

- [ ] Tell Rob about the different design checkpoints we need
  - Checkpoint re: Solutions page

Hey Rob, as we talked about during our chat we wanted to be able to use some frames and clips from the video as assets on our site and social media. Here are the different touch points we're hoping to get.

- Hero-style clip/frame of a "multi modal" agent that can make calls, use browser, and read docs
- A clip/frame showing how the SOP (agent instructions) map to what the agent does

# Thursday Dec 18 2025

### 📄 cmv-2.md (Last modified: 2025-12-18)

# Results

5.2 is winning

## Rule: Part 1 Section B - Plan of Insurance

1. 2+ instances of unclear rule

- 5.2 fails it because no checkbox is marked when "Other" is marked, but the rule doesn't specify anything about the "Other" case
  https://app.withpace.com/tasks/1d44762f-9f6a-4e8f-919f-86d23f40a2c2

## Rule: Part 1 Section C - Premium

1. Duplicate pages, one with checkboxes correctly filled and one without. The second page is presumably for overflow for other forms.
   https://app.withpace.com/tasks/17aa31b8-368b-4121-aa72-56ab1b8ee9f7

## Rule: Agent Checklist

1. Secondary addressee from not getting component gathered because rule doesn't mention how to handle it. 5.2 fails it
   https://app.withpace.com/tasks/269fef43-aa9e-4748-961c-1fd6e9f5336a
   Many many of these... 10~

## Rule: Part 2, Section C - Family History

1. Failed due to missing age at diagnosis
   https://app.withpace.com/tasks/e4eff7c5-1f81-4116-8d67-6397da15b4f7

## Rule: Section A. Business Information Questions 1-6

1. 5.2 failed because rule mentions MM/YY date and the date is MM/YYYY (lol).
   https://app.withpace.com/tasks/20d1f1cc-c0bb-4710-a029-3fa5b080068d

## Rule: Part 1 Section A Number 8 - Permanent, legal US resident

1. 5.2 failed because Visa type is "Unknown"
   https://app.withpace.com/tasks/61659dc1-dc89-4ad3-8470-cbbd840250bd

## Rule: Part 2, Signatures

node id : 6342f641-cb25-4294-bcee-4c8a4bc2bdd8

### CMV win [## INVESTIGATE IMAGES HERE]

Signed at (State) OR - things its Or not oregon <-- first real flag
https://app.withpace.com/tasks/5e94adf8-2580-4f9b-8387-589c085c41b7 <- OR
https://app.withpace.com/tasks/3d42886c-89df-4af9-adbb-79f944d3179f <- IL
https://app.withpace.com/tasks/3446b9ef-999a-4935-b329-fee3f71f2381 <- ID
https://app.withpace.com/tasks/2877d069-972b-4709-816d-ecc9b990d617 <- ID
https://app.withpace.com/tasks/fdc58eec-5574-4d1d-9254-690d7dbcd7a8 <- ID
https://app.withpace.com/tasks/17f815f6-4613-48da-91bf-8ed7935baccd <- ID

### 5.2 wins

https://app.withpace.com/tasks/cd265963-7132-44cd-b7d4-1d9a970afccb <- OK
https://app.withpace.com/tasks/151cc963-dc6b-4603-b919-5641c3c1406f <- OR
https://app.withpace.com/tasks/3cf73247-b1d8-400e-b322-a96aff2630ff <- OK

## Rule: Part 1 Section G - General Information

5.2 fails because "frequency" of travel is not mentioned for traveling outside the US
https://app.withpace.com/tasks/806ea624-63f6-42e5-893b-7729761c563f
https://app.withpace.com/tasks/7de3a46b-b27c-4bda-8bed-7adda30c86eb

## Rule: Part 1 Section F - Insurance History

1. Duplicate pages, one with checkboxes correctly filled and one without. The second page is presumably for overflow for other forms.
   https://app.withpace.com/tasks/683cd8cb-73b6-4539-9237-6dc39a888013
   https://app.withpace.com/tasks/62972c86-351a-46f5-bd68-43b57842379c
   https://app.withpace.com/tasks/a4bd0e3b-e5a4-42ff-a817-9d44cceae591

5.2 wins because it sees the product column correctly when CMV doesn't - https://app.withpace.com/tasks/13086794-90f7-4a66-a3dd-0e6069f69d28
5.2 wins because it sees type column correctly
https://app.withpace.com/tasks/21548806-994a-438b-9a1f-b428cd71ea55
https://app.withpace.com/tasks/2877d069-972b-4709-816d-ecc9b990d617
https://app.withpace.com/tasks/ba5281f8-c00a-4fbc-8e3d-ccee687bd101

## Rule: Section above Section A

Component gathering Cannot find the right supplement sections

## Rule: Part 2, Signatures Box, "I am not a U.S. person..." checkbox

Confusion between signed at state and rule. Rule could be written better.

- https://app.withpace.com/tasks/e294241f-b020-4598-82a0-581201e9be81

## Rule: Base Rating and Table Rating

Possible issue with not using contextual substitution. It is clearly understanding the issue.. Just the rule is unclear.

- https://app.withpace.com/tasks/e294241f-b020-4598-82a0-581201e9be81

Rating class confusion

- https://app.withpace.com/tasks/e4a8a0d9-d423-44c3-97ab-f8d9497d832b

---

- [ ] Roadmap ...
- [x] Write the damn blog post
- [x] Checkbox majority voting resolution - fix all the rules

- Agent letter
  [Added "Secondary Addressee Form" to ignore these checkbox items if they appear section]

- section f - insurance history
- section c - premium

  > Note that sometimes there might be two sets of Section C across two pages. In those cases, as long as a single set satisfies the constraints below, consider it a pass. If neither set satisfies the constraints, fail.

- section c - family history

  > A missing age of diagnosis is okay

- section b - plan of insurance

  > 2a. If "Other" is checked, we don't need a corresponding term length checked.

- Section G - General Information

  > 7a. For travel outside the US, do not fail this rule if only frequency is missing but other details are provided.

- Section A. Business Information

  > MM/YY -> mo/yr

- Base Rating and Table Rating
  The value of "Rate Class Table" is "@..."

- Part 1 Section A Number 8
  [didn't change]

- Part 2, Signatures Box, "I am not a U.S. person..." checkbox
  The proposed insured has mentioned that their state of birth is: "@Part_1_Application.Proposed_Insured_State_of_Birth"
  If the checkbox corresponding to the attached quote below is checked, then ensure that they didn't use a US state as their state of birth.

- [ ] Get Luke Presberg an api trace
- [x] Merge Luis' PR for pen test
- [x] Turn on routing for all non-accelerant orgs
- [x] Checkbox majority voting investigation

- [ ] Work on diff view for agents
- [ ] Work on gmail integration convex
  - Gemini thread https://gemini.google.com/app/0e7fb526dbc01ef1
- [ ] Evaluate differences for CMV
- [ ] Setup recurring pen test

**Agent reliability**

- [ ] Surface failure reason for send email tool call
- [ ] Roll run code tool into rest api tool
- [ ] Agent reliability - checklist / tags something like that

**Demo work**

- [ ] Caching taking 18 seconds to execute....
- [ ] Mark good runs / star or pin tasks and agents
- [ ] Read email tool not showing relevant output even if it succeeds
- [ ] Unclear where we got the email body that was sent out (agent vs hard coded)
- [ ] Confusion around what was published
- [ ] Confusion around which version was live
- [ ] Diff view / revert button for flow changes

# Tuesday Dec 16 2025

- [x] Respond to Varun about gmail connection
- [x] Investigate agent mail

# Monday Dec 15 2025

Mostly spent working on conversational agents. I think scaffold is in a good spot.
What's interesting is we need to make sure these following customer requests get satisfied. Specifically

- Accelerant: New text messages coming in many hours later need to get attached to the original task. Also need the ability for new messages to get their own new threads....
- IB&M: Multiple emails come in regarding the same Bond number. these all need to get attached somehow to the same task? Depends on what the situation is. if a task is waiting for action and we have an agent .. that needs to look things up by bond number or something like that....
- TMG: Same email with same entity id (message id) getting forwarded multiple times and we have to either create or attach
  - This is solved by DECOUPLING email message id from the entity id. It's kind of unrelated to the message router

- [x] Finish routing layer

# Thursday Dec 11 2025

### 📄 multiplayer.md (Last modified: 2025-12-12)

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
- [x] simple fix for update race condition is like... check if this current session is making the edits then don't overwrite the local.?

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

- bring state into the mdx - into the each node
  - minimal version is putting it into the node key
  - better version is having some kind of delimiting such that it's not a pita to read
- state comes from step node
- you only edit the step node
- for now we edit the actual node row in the db when the step node node gets edited
- need a nonce on the node to know if you need to update
- the mdx node value is just the json of the zod schema
- then........ you can just YJS or rushlight the whole document

## constraints

- few users.... simple doc

## random

- compaction?
- ot vs crdt

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

Given some directive like this, I want to be able to edit this with a custom React component. I want to define many different kinds of nodes, each with their own data type and each with their own React component. This React component could really be anything. It could be input sliders, text areas, buttons, whatever I want really. It should just be arbitrary React. And the interesting thing is I want to create some kind of binding where as I use these inputs, they edit the directive content underneath. So for example, you can imagine me having a radio button to set the `anythingReally` variable above to `true` or `false`.

I also don't want the React components to know about MDX, Markdown, or MDAST. I want them to just take in some value and a callback to edit that value. Then, some shared container component would serialize that incoming value and update the MDAST. So you can see there's this one bridge component and many many possible react editor components.

Consider the code here: apps/frontend/src/pages/Flows/Editor/components/flow-doc-editor/node-directive-descriptor.tsx
I have the beginnings of this directive here... Can you write a proof of concept of this feature with clean concise code and we can go from there. This POC should include all the features I've described above and two simple example child editor components that edit slightly different jsons. The child components should have some buttons, inputs, and a radio.

---

- [x] Send rob assets
- [x] Anthropic and 5.2 testing...

- [ ] Renaming issue for Rahul

- Agent might do better if we gave it specific milestones to "check off" - this could be interesting as an architecture thing
- Should we build a system of record?
- Should we build a UI layer on top of the agent for every use case that lets us knock this out of the park

# Wednesday Dec 10 2025

- [x] Spent half the day working on citation splitting its tough lool...

- Had a good conversation with Eric on working on higher leverage things -- agent is always in a state of degradation
- Basically RPA is in a decent spot
- Could be cool to have a self improving agent
- Integration of the agents and ease of use is doing to become a bigger thing over the next N months

- [ ] It's insane that I don't know the answer to this question myself. why is that? it feels so wrong. I need to think of a longer time horizon and come up with the answer myself

ChatGPT history with short term and long term memory architecture is kind of sick.. sliding window memory, facts memorized about a person.

purchase amount: 4 items
sell amount: 3 items
buy price: 10$
sell price: 40$

# Tuesday Dec 9 2025

- [x] Screenshots for Rob for the script
  - [x] Send him the specific parts of the website that we also want to backfill based on the video
- [x] Formula extractions / calculator extractions

Right now in @apps/backend/src/temporal/workflows/flow-agent/orchestrate-single-extraction.ts we have this new pattern where we split one large extraction call into separate temporal activities to better spread the load out. We want to similarly split up the citations flow into smaller chunks and call them as part of separate activities. The relevant code for this and some basic guidance is in @apps/backend/src/temporal/workflows/flow-agent/orchestrate-bulk-extraction.ts and also in @apps/backend/src/temporal/flows/cite-flow-model.ts

Could you implement this split?

## Capabilities

Existing capabilities

- Connecting to random APIs
- Reasoning over 50~ pages of documents to extract simple-medium complexity results
- Email/text back and forth - simple conversations (10~ turns)
- Filling out templated PDFs and excel files
- Navigating medium complexity websites
- Web Search, deep research
- Using our existing UI and design to show a BPO workflow

New capabilities
On the order of a few days

- Small improvements to document understanding and reasoning
- Generating a somewhat bespoke PDF or Word doc
- Filling out a Word doc
- Building a simple extension to our site with some new display type (ex: 1035 exchange history)

On the order of 1-2 weeks

- Direct integrations with any insurance system
- Deep investigation into 100~ pages of documents to put together a complex chain of hand offs
- Email/text back and forth - complex conversations (40~ turns)
- Filling out a medium complexity Excel file
- New visualization for a single kind of workflow (ex: )

On the order of a month

- Reasoning over and filling out a complex Excel file
- Custom view for a complex workflow that looks very different from current site

On the order of 3-6 months

- 95% reliability on complex voice calls
- 95% reliability on complex computer use

# Monday Dec 8 2025

**Urgent**

- [x] Deal: Canopius citations

Citation improvement ideas

- Split separately for each field
- Pick a list of boxes. Group boxes where possible
- Actually failed citations

**Misc**

- [ ] Issue with multiple tabs open for multiplayer?

# Friday Dec 5 2025

- [x] Elliot web search

**Voice evals**

- Can we get full call logs w/ transcript?

**Voice vibe**

- tone issues - too therapy or aggravated
- transcription accuracy
- interruption for email and phone number pausing

# Thursday Dec 4 2025

- [x] Debug cpu / memory issue (Kim's repro) - if done right, big dub in CPU
- [x] more logs to prevent main agent continuing voice stuff

# Wednesday Dec 3 2025

- [x] Heads down on tasks.....
- [x] Just designed all day Jesus

# Tuesday Dec 2 2025

Spent a bunch of time generating images for the launch.....

## Voice call evals

- Agent should end at this step
  const runId = "e996c335-15b7-4c7a-ab4a-c1c9ad68203d";
  const stepIdx = 1;
  const logIdx = 0;

- Agent should end at this step
  const runId = "b567b626-88d7-43a6-99dc-50e45dfb1213";
  const stepIdx = 1;
  const logIdx = 0;

**Thoughts for openai meeting**

- is anyone particularly proud of how they test and eval their agents?

- Testing the agent - how do you test this thing lol?
- Narrow down context? Top k?
- Web agents
- Caching
- Voice agent architecture
- Document understanding -- excel
- Document editing -- pdf, excel, word

durability for agent

- has to match how the model is trained
- model was trained on a specific "surface" (meaning their tools and and api, like apply_patch etc)
- build on the same abstractions the model was trained on - will have to baby sit prompts less

evals

- evals and tests are almost the entire problem.... if we have evals... what do we not have....

- custom tool for note taking can be good for performance.. (maybe useful for cor?)

At RYZE, AI isn’t just a tool — it’s a strategic enabler. Partnering with Pace allowed us to reimagine how quality assurance is done, creating a process that’s faster, smarter, and more consistent across every claim.
Walt Leddy
CEO

We’ve taken a step forward on our journey to modernize the customer acquisition process. With automated systems, our teams now have more time to focus on customer relationships, which supports Prudential’s broader goal of delivering industry-leading experiences for both clients and customers.
Sara Atkinson
Vice President of Customer Acquisition

# Monday Dec 1 2025

- [x] “Terminal status: [Dropdown, default Success]”

We should check in quickly around the productizing mid-market motion. Takeways based on past conversations..
Quick check in re: productizing mid-market motion - dyt still think that's valuable and if I should be filling in gaps there? Seems like Yonah, Chris, Arpan et al have a decent grasp on things. Curious about ur thoughts

- Can sell past use cases: focusing mostly on voice and claims QA
- I think we could sell claims qa repeatably and I think Arpan could do it
  - Over the last month seems they're doing much better on the demo
  - Library of use cases so we can reference what other customers are doing
    - In the call we have an opportunity to impress that we really know their industry.
      - Recently in a call, their use case was water mitigation so I mentioned some of the rules I saw in the Ryze water mitigation use case like parsing dry logs and PPD calculations and you could see them light up
      - If we can do this every call, and have the GTM team understand our rolodex of agents and cases we'd be able to make this much more repeatable
    - Our demos are perhaps too simplistic (check very basic values) -- we should be checking more complex values (ex: calculator agent, photo rules, etc.)
- There are relatively few claims QA customers - none are particularly big.
- How are you feeling about progress so far?

* [x] Propose new website structure for /customers page
* [x] Respond to David

# Friday Nov 28 2025

- [x] Prototype multiplayer

# Thursday Nov 27 2025

### 📄 page-site-concepts.md (Last modified: 2025-11-27)

# v2

life
carrier
mga
broker
p&c
annuity
group benefits

## life

hero:

- complexity of life insurance procedures uniquely lend themselves to agentic solutions
- revamp your life insurance operations with ai

- taxonomies of life carriers

## p&c

- urgency of underwriting

## group benefits

- manual nature of onboarding

## annuties

- quadruple your capacity
- agents don't have capacity, let the interest rates change

---

# Reflection

I'm not convinced that we're much more productive than if just me and Eric were working
Everyone else is almost just barely net positive - there's a lot of everyone trying to be an FDE

- is this true? do i actually believe this?

After being on a few of these mid market calls - I think the high level takeaway of what I think we need to close mid market

- Keep the workflows aggressively simple. 4 instructions of 4 words each. "read the email, extract the documents, upload to guidewire"
- Show how we can deliver complex edge cases - on one of the calls the customer got really excited when I mentioned something (dry logs for water mitigation) that showed I really understood the workflow.
- If we could have then shown that in the product I think that would have landed really well.

I think a lot of product lines would have benefited from me scaffolding them out ahead of time
Ex: w/ voice some bad decisions made (ex: transient agents, weird integrations w/ agent loop) that if we got ahead of would have saved us a few days of work

- I think its hard to do via review close to demo because
- I think we can get ahead of some of these future requests by looking at near term roadmap (1-2 months) and me scoping out the initial architecture and experiments

There's a loose fear that if we had to build extraction today we might not even be able to do it lol

Loose thoughts on the state of me and the company
Lots of random conversation from first principles
Should just have DRIs that over time will become engineering managers or tech leads or whatever we want to call it
Some resetting of cultural goals - the most important things are to (1) deliver value to existing customers and (2) close new business

I think, candidly, it feels like I've been wasting a lot of time over the last month.
Why don't we wrap up this mid-market product stuff, and then see where I can drive unique value?

- It seems like they've actually got it.
- We just need to keep the demos and the sop simple.
- We need to focus the demo on the outcome.

Let's carve out a specific talk track for a mid-market demo and for an enterprise demo.

- Mid-market focuses on outcomes, simplicity, ease of use, templates, and people working with the product easily via email and integrations
- Enterprise focuses on reliability, API access, power accuracy, repeatability, and scale.

I think there's a few paths forward for me [don't say this]
I think overall I've been letting the work drive me instead of actually driving the work forward.
I'd love to stay close to the customer and do specific customer stuff.
One thing is I'm definitely doing a lot of stuff that is not stuff that uniquely I can do. It's stuff that really anyone or codex can just knock out.
I'd prefer to just hand all of that off to someone else and drive forward on big needle movers.
I also need to spend some time guiding other workflows (ex: voice) because they're starting to set up bad foundations that are going to bite us in the near future.

# Wednesday Nov 26 2025

### 📄 cmv.md (Last modified: 2025-11-26)

# Part 1 Section E Beneficiary details

# Wins Losses

Reducto 4 1
Gemini 5 0
CMV 1 4

# Part 1 Section F Insurance History

# Wins Losses

Reducto 2 1
Gemini 0 3
CMV 1 2

Reducto wins
N1125250 https://app.withpace.com/tasks/5c6701eb-e2ca-4979-b9c4-ac21ad437ac4
N1131955 https://app.withpace.com/tasks/d4d9fab9-348c-4075-86f9-95964fe3e3ae

# Part 2 Section C Family History

# Wins Losses

Reducto 0 0
Gemini 0 0
CMV 0 0
Unclear 3

N1110580 - https://app.withpace.com/tasks/45060746-a8bc-4e06-a75c-9e83594fc97e - missing age at diagnosis - https://app.withpace.com/tasks/c6b7c9aa-f091-405e-8249-a1755b57a646 - third

- reducto fail, others passed

# Part 2 Section D Medical Information

# Wins Losses

Reducto 7 3
Gemini 10 0
CMV 3 7

No diagnosis for q5 - 7

# Part 2 Signatures box, i am not a us person

# Wins Losses

Reducto 0 3
Gemini 1 2
CMV 3 0
Unclear 0

Reducto + gemini looking at Signed at state issue 2

# Part 2 Signatures

# Wins Losses

Reducto 4 3
Gemini 5 2
CMV 3 4
Unclear 0

# Section A Business Information Questions 1-6

# Wins Losses

Reducto 2 1
Gemini 3 0
CMV 1 2

---

- [x] Review rodrigo pr
- [x] Verify Gemini results for checkbox majority voting - sent note in intelligence
- [x] Gemini results for checkbox majority voting... -- work with Tristan to roll out specific rules

# Tuesday Nov 25 2025

- Zurich na demo help
- Prudential scrolling virtualization

- [x] Website meeting with chris
- [x] make Ryze image logo thing
- [x] OpenAI run evals
      Did this for a bit .. okay . Lesson learned, save this work in a PR so you don't have to recreate it....
      Need to timebox it because it takes up a lot of time. Just send some results to Luke and lets move on
- [x] Verify caching for demos -- seems fine?
      One issue: changing steps can change the extraction cache logic

## Chris site feedback

- More CTAs on product page
- Represent the paper ai diagram slide on the website

Lots of random conversation from first principles
Should just have DRIs that over time will become engineering managers or tech leads or whatever we want to call it
Some resetting of cultural goals - the most important thing is to keep the customer happy

# Monday Nov 24 2025

- [x] Investigate issue with read email appearing then disappearing (system message parse issue?)
- [x] Investigate Janushi
- [x] Respond to Kevin

Hey Kevin, we have some design improvements to the Editor we want to make building on your foundations. Since the original design we've expanded upon our Voice and Web agent capabilities. I'm including 2 looms from our team members who lead those features walking through how we could make that experience better. Let us know if you have any questions or clarifications!
https://www.loom.com/share/c829769c58e14f41b9d7665fd2094e45
https://www.loom.com/share/096710e4bf3745a88ee057b3f8bc4414

Misc. thoughts

- Feels like I'm not doing anything useful on voice - slow progress
- Would be good if I just reviewed more aggressively
- Re: mid market stuff - I've seen a couple calls where the demos went well - blue grass tower hill (exactly ryze use case) and ocean harbor.
  - I actually don't think we need any significant product changes to support this market because their agents are very simple
  - I think for the demos what we need to do here is make some of the rules and extractions more interesting

## Reducto vs CMV tally

### Beneficiary details

See special requests

### Signatures

Reducto - 2
CMV - 1
Rules - 2

### Medical information

Reducto - 6
CMV - 1
Rules fix - 2

## Tower Hill Blue grass

- Looking at dry logs - mentioned went over really well
  - Equipment Decontamination
  - PPD calculations
  - Air fan usage
  - Dry log goals
  - Moisture readings
    Tailor a demo to their specific kind of TPA handling as much as we can. It would have been nice to show them a complex rule instead of generic rules like the date of loss being inconsistent.
    Complex rules can involve calculations and photo rules..

Lots of random stuff to do... rough order of priorities is to handle all the voice stuff first
and then focus on other stuff.

## Jack Adolfson

- Big holdback - lack of structure - not a
  pros: grit, creativity, process, build up
  cons: bad demo, bad structure

# Friday Nov 21 2025

## Pru oncall issue

Need to fix alerting / process such that a big backlog like this triggers a much bigger response asap

What kind of guardrails are people using to make their agent more deterministic?

Agent issue: Model passing in "string": "[Object object]" to the run code tool - TMG

I should probably put unbounded tasks at the end of the day unless they're incredibly important.
By that logic Gemini would be at the end.

# Thursday Nov 20 2025

- [x] voice x main agent - support received information
- [x] Add Gemini to logs

## zurich na

met chief claims officer at a conference
huge insurer
this business is mostly commercial, specialty, work comp, commercial auto, commercial property
worth going over and above on this demo
would like to show an 80/20 version of the demo

2 demos

1. claims qa

- proactive QA - check very claim before it goes out the door
- line item complex rules consistency

2. fnol

## quotes on home page

We’ve taken a step forward on our journey to modernize the customer acquisition process. With automated systems, our teams now have more time to focus on customer relationships, which supports Prudential’s broader goal of delivering industry-leading experiences for both clients and customers.
Spike Lipkin
CEO, Newfront

At RYZE, AI isn’t just a tool — it’s a strategic enabler. Partnering with Pace allowed us to reimagine how quality assurance is done, creating a process that’s faster, smarter, and more consistent across every claim.
Walt Leddy
CEO, RYZE Claim Solutions
