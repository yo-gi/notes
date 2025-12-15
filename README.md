# TODO

## Ideas

- [ ] Devin style "Browser" / "Voice call" tab design
- [ ] Give quick overview on all the use cases that customers are using Pace for

## Problems

- [ ] Shared set of entities for child agents instead of cloned entities

---

# Thursday Dec 11 2025

- [x] Send rob assets
- [x] Anthropic and 5.2 testing...
- [ ] Routing layer
- [ ] Setup recurring pen test
- [ ] Investigate agent mail
- [ ] Renaming issue for Rahul

- Agent might do better if we gave it specific milestones to "check off" - this could be interesting as an architecture thing
- Should we build a system of record?
- Should we build a UI layer on top of the agent for every use case that lets us knock this out of the park

# Wednesday Dec 10 2025
- [ ] Surface failure reason for send email tool call
- [ ] Roll run code tool into rest api tool
- [ ] Agent reliability - checklist / tags something like that
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
- [ ] Screenshots for Rob for the script
  - [ ] Send him the specific parts of the website that we also want to backfill based on the video
- [ ] Formula extractions / calculator extractions

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
* Split separately for each field
* Pick a list of boxes. Group boxes where possible
* Actually failed citations

**Voice**
- [ ] improve tool call prompting
- [ ] voice tools return entity id
- [ ] send entity ids to voice agent
- [ ] send voice agent all main agent created entities
- [ ] reduce tool boilerplate

**Demo work**
- [ ] Caching taking 18 seconds to execute....
- [ ] Mark good runs / star or pin tasks and agents
- [ ] Read email tool not showing relevant output even if it succeeds
- [ ] Unclear where we got the email body that was sent out (agent vs hard coded)
- [ ] Confusion around what was published
- [ ] Confusion around which version was live
- [ ] Diff view / revert button for flow changes

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

* Can sell past use cases: focusing mostly on voice and claims QA
* I think we could sell claims qa repeatably and I think Arpan could do it
  * Over the last month seems they're doing much better on the demo
  * Library of use cases so we can reference what other customers are doing
    * In the call we have an opportunity to impress that we really know their industry.
      * Recently in a call, their use case was water mitigation so I mentioned some of the rules I saw in the Ryze water mitigation use case like parsing dry logs and PPD calculations and you could see them light up
      * If we can do this every call, and have the GTM team understand our rolodex of agents and cases we'd be able to make this much more repeatable
    * Our demos are perhaps too simplistic (check very basic values) -- we should be checking more complex values (ex: calculator agent, photo rules, etc.)
* There are relatively few claims QA customers - none are particularly big. 
* How are you feeling about progress so far?

- [x] Propose new website structure for /customers page
- [x] Respond to David

# Friday Nov 28 2025
- [x] Prototype multiplayer

# Thursday Nov 27 2025

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
* Looking at dry logs - mentioned went over really well
  * Equipment Decontamination
  * PPD calculations
  * Air fan usage
  * Dry log goals
  * Moisture readings
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