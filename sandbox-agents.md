# TODO

- [x] We need tool preambles from the agent. Now that I think about it I think the reasoning is missing completely. It is now showing separately.
- [ ] Sub agents for stuff like extraction / cua / voice
- [ ] Persistence for longer running agents. Can we actually just add a new set of DBs and then we can also make sure we add a row to task and run and we'll get the data there.
- [ ] Figure out how to integrate with reporting. Maybe this will just be based on results.......

- [x] Figure out how to eval the Openai requests. Specifically just skills as UAR is python...
- [x] RFC for the agent migration
- [x] Optimized for working with Openai -- Luis is handling
  - [x] Testing excel spreadsheet skills
  - [x] Testing misc. skills
  - [x] Having a better understanding of the sandbox environment

Agent will load its own messages on load with an agent id by inspecting ndjson 