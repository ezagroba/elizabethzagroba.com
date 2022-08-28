.. title: Talk About Your Test Strategy
.. date: 06 June 2022
.. tags: communication, testing, 
.. previewimage: /images/posts/2022/megaphone.jpg
.. description: State explicitly what you hope to achieve and how much effort you're willing to spend getting there.

I was invited to join a team's debate this week about what environment to point our third-party security testers towards for their upcoming penetration test. I asked what I thought was both an obvious question and something worth discussing with the team: 

"Do we want them to identify security risks, or are we just checking boxes here?"

A combination of stunned silence and nervous giggling (muted over Zoom) ran through the team. "We don't talk about that out loud," the team lead told me. 

But that's exactly what I'm there to help uncover as the Quality Lead for this team and the others in our unit: how deep or shallow should our testing be? If our testing uncovers issues, are we interested in mitigating them? [If not, why are we testing?](https://elizabethzagroba.com/posts/2020/2020-05-24_if_a_test_falls_in_a_forest/)

## A Test Strategy in Five W's

This conversation took me back to a few years ago. I was working on a product in a phase before production-level quality that we dubbed "demo-driven development" in retrospect. We were showing off a combination of Powerpoint slides and small pieces of the product in order to gain more funding. A person interested in testing but with too large a scope to pay attention to my team in particular asked me for a test strategy.

But the demos kept changing. What was important this week wouldn't be important the next. There wasn't a lot of exploratory testing being performed or automated tests being written. All my time was occupied in figuring out what had already been promised, what we were trying to sell, and filling in the gaps between those with a very specific path our product owner would follow during a demo, down to browser and screen resolution. 

I asked the person who wanted the test strategy document what they were going to do with it, what it might be used for. They sent me the enormous table where a link to my test strategy would be added, and clearly never looked at or noticed again.

Could I document in an official test strategy document for my team that I wasn't doing much testing? It turns out, yes. 

I outlined the document with the five w's: who, what, when, where, and why. The whole document looked something like this. I don't think you even needed to scroll to read it. 

- Who: Our stakeholders are the people we're selling to, our product owner, and our team, in that order. 
- What: We're testing one particular happy path in Firefox (our product owner's default browser).
- When: Due to the volatile nature of our product's priorities, our minimal testing has been concentrated after user stories are completed.
- Where: We're running the application locally for demos. We haven't had a chance to set everything up we'd need to have in a hosted environment.
- Why: We test to ensure that the one happy path is demonstrable to a customer in a demo, and to provide our product owner with the work-arounds for the gaps in our product. 

I sent it to the person, expecting them to get back to me and tell me I couldn't do testing like this. Or at least, I couldn't write it down. But they never read the document! They thanked me, linked it in their table, and went on their merry way. 

## A Test Strategy in Stakeholders and Risks

I liked the way I shaped my test strategy around the very specific set of stakeholders and their risks in the five w's strategy. I wanted to bring this same connection to the teams I support when I started as Quality Lead for my unit. I ran a test strategy workshop for each of them to identify their stakeholders, talk about the risks that matter to them, and see how their team activities mitigated those risks. I got to this Miro board template after a few rounds. 

1. List the software the team is responsible for. (Our teams typically have legacy products they're maintaining in addition to the new things their roadmap focuses on.)
2. Mind map the stakeholders for these products. 
3. Add stickies next to the stakeholders' names with their possible risks and concerns.
4. Review the types of testing activities (things like exploratory testing, reviewing the production logs, static code analysis, etc.) for comprehension and completeness. 
5. Move each testing activity onto the impact (it's important vs. it's not important) and priority (we do this vs. we don't do this) quadrants.
6. Vote on stickies that landed in an unexpected spot.
7. Talk about the most-voted stickies in order, and identify action points with owners from there.

Part of this workshop was to show the teams that not every piece of testing is something that matters to the stakeholders. I didn't expect them to do every possible kind of testing imaginable. But I did want them to all understand and agree what kinds of testing they were and weren't doing. I got them talking about it out loud.

## A Test Strategy Derived from a Vision

Believe it or not, a one-time workshop was not enough to get everyone to identify and build the perfect test strategy! As the teams grew and the workshop faded from memory, I got questions about the test strategy for the teams. I heard about goals of "bug-free software" and asked about "what best practices to follow" to get there. 

As fun as it would be to pontificate about how [there is no such thing as bug-free software](https://app.thestorygraph.com/books/8ba29269-1843-4ac1-be0c-226752b17937), and [there are no best practices outside of the obvious domain](https://www.jrothman.com/wp-content/uploads/2014/03/Cynefin.jpg), that doesn't help people know what to do. So I wrote a "Quality Vision" document. (Pro tip: use a noun you wouldn't use for anything else so it's easy to pull it up by typing "vision" in your browser bar.) The Quality Vision for the unit places trust in the expertise of the teams to choose their own ways forward. It has things like: 

- **Is our product at the right level of quality to release right now?** This is a constant conversation between the development team and your product owner. Think about the risks and concerns of the customers you're targeting.
- **Data Security** We're not to use production/customer data for development purposes outside support incidents. Here's a link to a more in-depth document from our Security team.
- **Reliability** Here's a link to the document of what we promise our customers in our service-level agreement. 

It's not going to tell you what the right answer is for your team right now, but it'll give you some things to point to when you're discussing quality with your team. 

---

Because after all:

Quality is value to some person who matters at a particular point in time.

For the penetration test, the team lead quickly followed their "We don't talk about that out loud" comment with a "why not both?" jest.  Why can't we both check the boxes for the authorities, and uncover valuable information that we want to act on? 

Indeed, that's where we landed. We decided to point the security team to the production environment because that would reveal the best information. Unless that setup takes too long for the team, then we'll point them to the test environment. But regardless: we'll tell our bosses and our product owner what we're doing and why. We'll talk about our test strategy out loud. 

How have you started a conversation about quality with your team? When have you decided not to test something? What have you not tested and also not discussed?

![](/images/posts/2022/megaphone.jpg)

Photo by [Patrick Fore](https://unsplash.com/@patrickian4) on [Unsplash](https://unsplash.com/)