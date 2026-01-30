# TODO

- [x] We need tool preambles from the agent. Now that I think about it I think the reasoning is missing completely. It is now showing separately.
- [ ] Sub agents for stuff like extraction / cua / voice
- [ ] Optimized for working with Openai -- Luis is handling
  - [ ] Testing excel spreadsheet skills
  - [ ] Testing misc. skills
  - [ ] Having a better understanding of the sandbox environment
- [ ] Persistence for longer running agents. Can we actually just add a new set of DBs and then we can also make sure we add a row to task and run and we'll get the data there.
- [ ] Figure out how to integrate with reporting. Maybe this will just be 
- [x] Figure out how to eval the Openai requests. Specifically just skills as UAR is python...
- [x] RFC for the agent migration

- [ ] Store the full request response trace so that agents that get interrupted can pick back up. Store logs with an agent id that temporal provides and on startup we can look for those logs.
- [ ] Change the extract tool such that it ends right after you kick off all the subagents and then the subagents are just responsible for writing to the result file -- need to find a way to do this atomically so there are no race conditions....