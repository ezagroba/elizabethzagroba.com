.. title: The Long Haul
.. date: 8 May 2021
.. tags: testing, teaching, career, critical-thinking, humans, mindset, leadership

I've been both the lead of my team and a tester on that team for a year now. Getting answers, adapting to change, and identifying solutions have completely different time horizons in each of these roles. 

---

### Tester experiments

Testing experiments can run quickly. A testing experiment might look like this:

1. Call an API
2. Inspect the output
3. Compare that to the specification
4. Question whether either or both need changing
5. Talk to a developer about the changes
6. Update the specification and/or tests

All of that happens within minutes or hours, or days if schedules are extremely incompatible and asynchronous communication is failing. I can be confident in the experiment's outcome. I can weigh the relative merits of caring vs. not caring about a particular error response code or required field, and leave my work at work. The next time I see a particular error response, I know what to look for and where changes might be needed. A failing test is evidence that something used to work in a particular way. 

### Team lead experiments

Team lead experiments take longer. A team lead experiment might look something more like this:

1. Team members complain that it's hard to get their ideas in during refinement.
2. I mention this to the talking-dominant team member at a 1-on-1.
3. Talking-dominant team member dominates following refinement.
4. I remind talking-dominant team member in Slack about our previous conversation.
5. Talking-dominant team member spills over their allotted time during big unit meeting.
6. I bring both of these instances in our 1-on-1, sharing the consequences (they're the single point of failure, other team members aren't heard) of their actions.
7. Talking-dominant team member does it again.
8. I ask team member what I can do to help them change their behavior, given that we are both adults in control of our own behavior. They agree that change is their responsibility. We agree that setting their microphone on mute at the start of the meeting would help.
9. Talking-dominant team member dominates some of the following refinement, until I remind them to mute, after which other team members have time to think and contribute too.
10. I ask talking-dominant team member to set up a Slackbot to send them a reminder to mute their microphone each week before the meeting.
11. Other people are able to contribute at the following refinement. 

This took place over months. We're not to a point where we have a solution that works every time. I went in with a different hypothesis each time, not knowing when I'd hit on the right one:

2\. I think the talking-dominant team member isn't aware of their behavior.  
4\. I think the team member has forgotten our first conversation.  
6\. I think the team member doesn't understand the impact of their behavior.  
8\. I think the team member hasn't found a tool or a trigger to change their habit.  
10\. I think the team member needs both a tool and a trigger to change their habit.

Any of the first four experiments taken by itself looks like a failure. The talking-dominant team member prevents other team members from contributing effectively. It takes me time as a leader to come up with a different hypothesis, try something else, and discover where to go from there. And this was a relatively straightforward issue to assess. Imagine how long it might take to find an effective response to a problem with more variables and more consequences.

--- 

I'm also thinking not just about the experiments themselves, but how they might come across to the wider team. For the testing experiment, I could present my results in standup the next day as "I tested it, everything's good" but it's more valuable for everyone if I [tell a bit more of the story](https://www.ministryoftesting.com/dojo/lessons/defining-story-completion-as-a-software-tester). In the team lead experiment, I can imagine my team member telling my boss "Elizabeth told me to be quiet" or me telling my boss "The talking-dominant team member is giving room for others to contribute." Telling a slightly longer story of the journey displays my value as a team lead in a better light. 

What experiments are you running right now? Is something that looks or feels like a failure getting you closer to a solution? How long is your time horizon?
