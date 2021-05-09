.. title: Questions from Exploratory Week on Writing Exploratory Testing Charters
.. date: 1 May 2021
.. tags: testing, charters, exploratory-testing, risk-based-testing, teaching
.. previewimage: /images/posts/2021/MoT.jpg

The Ministry of Testing hosted a week all about exploratory testing. I had the honor and privilege to help shepherd a small group of testers on the path of writing charters for their exploration. The most interesting part for me is where people had questions. It helps me figure out what sunk in, what could use more explanation, and helps me know that I've answered at least one person's burning question. Here are some of the ones I remember from the live Q&A at the end:

### Q. Do you use the word charter?

A. Basically no. I've only heard testers who've specifically dug into this topic use the word charter. Almost all of the people I collaborate with on a daily basis (developers, product owner, UX, managers, other testers) do not have this as part of their experience. Most of my colleagues are not working in their first language. As a native speaker, I need to have more than one word to describe any particular phenomenon in case the first one doesn't resonate, or isn't understandable in my accent. (Everyone has an accent.) I've called charters:

- questions
- missions
- paths
- plans
- goals
- investigations
- journeys

It's less important to use the word charter than it is to get across the intent: you're going on an exploration, in a particular direction, with specific set of tools, and you hope to come away with more information on this topic than when you set out. Sharing your charters helps you get feedback about where to look more deeply, more broadly, and [where not to look at all](https://elizabethzagroba.com/posts/2020/2020-05-24_if_a_test_falls_in_a_forest/). 

### Q. Where do you bring charters up?

A. Where *don't* I bring charters up? It bleeds into conversations I have about my work. [Sharing my work and getting feedback about it is what ensures I'm providing valuable work for my team in the right direction](https://youtu.be/SM57HMJpkZc?t=974). I tend to discover points of interest for my developers once or twice a day when development is starting, and more often when testing is at its peak, which often escalates to pairing. Here are some other moments in time where I share charters: 

#### Standup
It's how I explain what I tested yesterday, what pieces I might have time for today, and what directions I haven't or won't have time for before we want to release the story. Sharing where I'm looking prevents me from being the one gatekeeper on quality for our product. "I've successfully called the API as an admin user and a regular user. Today I'm going to dig into what happens with the non-required fields." will solicit a completely different type of feedback than "I have an hour or two left on this story."

#### Refinement
Any clues I can give my team about what I'll be looking into, what kind of test data I might set up, and what tools I'll be using to test a particular feature will help them figure out the whole scope of the story. "I'm going to try names at the character limit to see how they wrap on the page." helps us all figure out that we need to talk about our expectations for a character limit, we need to talk to UX about what should happen when you try to input something too long, I need to test what happens on the API side for the same field, and we might need a frontend dev to help us with the wrapping or truncation depending on what UX decides.

#### Testing starts executing
This is the point in time where there's enough built that I can add test execution to the setup and planning I've already been doing on a story. It might be that the API spec is published, it might be that the application has one happy path built. The developers are still going, but there's somewhere for me to start. Depending on the size and complexity of the story, I'll reflect for myself, or share my ideas with someone else on the team. If it involves an integration with another team, I'd reach out to them too. 

### Q. Isn't that just a test case?

A. After almost two hours of technical difficulties and explaining things, I have to say I did not write the most elegant charter as an example during the workshop. You got me! I'm glad that this workshop participant has a good feel for what is too specific or too broad. I find this so hard to explain because so much of that depends on the context. 

But it wasn't terribly important to me to get the level of detail correct. Charters are a place to reflect on your testing and spark conversation. This charter did exactly that. 

---

You can find other questions there weren't time for during the workshop on the [Ministry of Testing club](https://club.ministryoftesting.com/t/wander-with-a-purpose-writing-charters-for-your-exploratory-test-sessions/49746). The [slides from the workshop are on github](http://ezagroba.github.io/charters). 