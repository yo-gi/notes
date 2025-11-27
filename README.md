# TODO

## Takeaways
- [ ] Add calculation to claim demo
- [ ] Add photo rule to claim demo

## Ideas
- [ ] Devin style "Browser" / "Voice call" tab design
- [ ] Give quick overview on all the use cases that customers are using Pace for

---

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

I don't think 

# Wednesday Nov 26 2025

- [x] Review rodrigo pr
- [x] Verify Gemini results for checkbox majority voting - sent note in intelligence
- [ ] Move to new website
- [ ] Propose new website structure for /customers page
- [ ] Respond to David
- [ ] Investigate CPU/memory -- can we make this scaling better
- [ ] Gemini results for checkbox majority voting... -- work with Tristan to roll out specific rules
- [ ] Pass entity ids and model names and whatnot from backend to frontend - initial message - can this be a control message?
- [ ] voice x main agent - support extraction -- setup with the previous.... - just expose all tool calls?
- [ ] Caching taking 18 seconds to execute....
- [ ] Mark good runs / star or pin tasks and agents
- [ ] “Terminal status: [Dropdown, default Success]”
- [ ] Read email tool not showing relevant output even if it succeeds
- [ ] Unclear where we got the email body that was sent out (agent vs hard coded)
- [ ] Confusion around what was published
- [ ] Confusion around which version was live
- [ ] Diff view / revert button for flow changes

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