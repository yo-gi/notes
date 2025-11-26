# TODO

## Takeaways
- [ ] Add calculation to claim demo
- [ ] Add photo rule to claim demo

## Ideas
- [ ] Devin style "Browser" / "Voice call" tab design
- [ ] Give quick overview on all the use cases that customers are using Pace for

---

# Wednesday Nov 26 2025

- [x] Review rodrigo pr
- [ ] Gemini results for checkbox majority voting
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