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
- [ ] Fix misc errors
  - Error 1: eval dataset has wrong entity because merge doesn't consider old entities?? this is a merge issue
  - Error 2: rule is missing model enrichment value
  - Error 3: 
- [ ] Fix various eval failures
- [ ] Find a way to handle vision -- basically just answer synthesis as a tool..???
- [ ] Embed documents as part of ingestion
- [ ] Generic agent interface that we can plug different pieces of tools into and it will search whatever
- [ ] Run it on prod against actual extractions
