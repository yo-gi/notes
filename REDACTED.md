# Friday Feb 13 2026

- TMG sync
  - Agent V3 skills to make API calls and run script
  - What's the priority of each of these things? Is there anything that's going to get them to have a wow moment?
  - What mental state are they in now and where Do we want them to be

Feedback

- I'm glad you're pushing on a lot of this marketing stuff - I think virtually no one at this company has that instinct so its great that you're pushing that forward
- I think for the TMG stuff I think the info could have been brought forth in a clearer way - like they are expecting to renew by X date, we want to show them this 2 months before, and this is the list of stuff we need to address. I'm not actually clear on what exactl
- Feedback around focus
  - I would encourge less time spent tweaking the infra side of our dev setup and more time focusing on building our product features. I think the changes can often be disruptive if you're not spending time socializing the idea with the engineers and getting everyone bought in.
  - I think the benefit of the FDE role is that you're really close to the customer and I would encourage your PR contributions to be more product- and customer-specific.
  - I saw that you had created a ticket to update turbo and then you tagged my PR to update turbo - is this really the right way to spend the time? Is this of the utmost importance? Will this help anyone move faster?

- Feedback around communication style
  - I think you're often excited about things and are knowledgeable about a lot of stuff but this manifests often as like rambling or nitpicking off topic thigs. I'd encourage you to have a higher bar for what you communicate on slack and in person - like does this really need to be said

# Thursday Feb 12 2026

(scheduling this message for after your onsite)
I think Varun's gotta go

- Sucks all conversational energy out of a room - bad for meetings, morale
- Time suck for team -- people spend time talking about how much they can't stand him
- Don't trust him in front of candidates
- Don't trust him to represent the company or the customer well
- By default rubs people the wrong way
- Spends a bunch of time working on worthless things and nitpicks
- Given how encompassing negative qualities are I don't think its coachable
- Contributions don't make up for the all negative impact

For context, I haven't really felt like this about anyone else in my career - am surprised

# Monday Feb 2 2026

---

Apologies, following up on this, I think we talked about some of this on the weekly today but update on the general situation -

We'll want to do some editor changes to accomodate the file system+new capabilities, fix existing pain points

- Simple view that shows files available to the agent
  - Uploading SOP, reference docs, etc.
- Getting rid of embedded tools in the editor (since we're removing tools from the agent, MDX has caused many issues)

Unfortunately we lost some time because a lot of the initial design exploration we did with Darek is based working with the old agent and I don't think its applicable in the new world. We have reset him on the new set of requirements.

I think the biggest unlock for agents out of the box will be enabling the "chat with your SOP" feature. If we can get to some kind of "claude code for insurance workflows" type feeling - where users just ask for changes and they happen, I think that would be big and is currently what I'm guiding the project towards.

Kim is working on on the editor experience and I'm working on getting the agent off the ground.
