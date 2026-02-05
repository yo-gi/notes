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
