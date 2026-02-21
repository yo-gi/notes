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
