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
  - Error 1: eval dataset has wrong entity because merge doesn't consider old entities?? this is a merge issue
  - Error 2: rule is missing model enrichment value
  - Error 3: "consider every single chunk" type use case. Rule looking for spelling issues, the search agent is not optimized for that
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

- Error 4: Thinks question 6 is blank but its not
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