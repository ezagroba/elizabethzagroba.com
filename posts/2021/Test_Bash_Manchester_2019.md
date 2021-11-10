.. title: TestBash Manchester 2019, The Last One
.. date: 10 November 2021
.. tags: testing, conference, testbash
.. description: I revisited my notes from TestBash Manchester 2019. Here's how they strike me now.
.. previewimage: /images/posts/2021/growthvsfixed.jpeg

I didn't know in September of 2019 that TestBash Manchester was the last TestBash I'd be attending for a while. I've revisited my notes from the workshop Joep Schuurkes and I ran about test reporting several times since then: for a video series, an [Ask Me Anything](https://www.ministryoftesting.com/dojo/series/testing-ask-me-anything), a [forum thread](https://club.ministryoftesting.com/t/ask-me-anything-test-reporting/46827), a [99-minute workshop](https://www.ministryoftesting.com/events/essentials-an-introduction-to-reporting-your-testing), and a [blog post](https://elizabethzagroba.com/posts/2021/map_out_your_stakeholders/). I'm just revisiting my notes now from the talks I was able to attend in the couple days after our workshop.

---

My notes from Pierre Vincent's talk on observability read like a wishlist of features I'd already been asking for in the app I was testing: unit testing, centralized logging, trace ids for integration debugging, etc. The app was also in a private beta at the time, so data collected from production would be filled with more anomalies than patterns. I'm still discovering how much more influence I have in my new role as Quality Lead to present the impact and influence the improvement of testability features.

Dan Smart and Yong He spoke about failure. The quote "Hey failors, how's the failing?" captures the essence of their talk: expect failure, and celebrate it, together. I get psyched anytime distinguishes between a fixed and a growth mindset as they did, which I still find best described in [this Marginalian (formerly Brain Pickings) piece](https://www.themarginalian.org/2014/01/29/carol-dweck-mindset/). 

I see in my notes from Conor Fitzgerald's talk on Kanban that kan = visual and ban = card. In the two years I spent running a Kanban team in the meantime, I can't remember how many times a week (a day? a minute of standup?) I asked "should we visualize that on the board?" Two of my big legacies on my former team were reinforced by Conor's talk: 1) eliminating of context-switching, and 2) not waiting until the retro to make changes.

"What does it mean to be responsible for quality?" asks Past Elizabeth to Present Elizabeth from the notes on Gary Fleming's continuous testing talk. It doesn't have a straightforward answer, and exploring this is part of what my job gets to be now. Some of his examples (separating deployment from release, example mapping) are what I get to inspire my whole department to consider as part of their strategy. 

Saskia Coplans's talk on security testing really stuck with me. Her ability to make the unnamable company she consulted for a joke every time she mentioned it was a level of comedy I can only dream of aspiring to in a talk. Familiarity with the STRIDE model and the OWASP Top 10 gives me a leg up in thinking about how to identify and mitigate risk in our software. 

Areti Panou's talk about a deployment pipeline resonates more deeply now, after two years of running and maintaining a pipeline, than it did at the time, when a pipeline was just a glimmer in the eye of a teammate. I held an expectation setting and reaffirmation workshop about one pipeline in my department last week. Areti's expectations that a pipeline should have a clear purpose, failure criteria, and fix deadlines could help fix the bystander effect I've experienced myself. 

The incomparable and unstoppable Lisi Hocke gave a talk about becoming more code-confident that still influences how I approach goals and objectives. Specifically: it's ok to re-evaluate if goals should still apply, and to establish pause or exit criteria to know when to give up. While I can be strong in saying no to what others expect, giving up on something I expect of myself can still be a struggle. 

Bill Matthews's talk on technical risks with AI prompted me to add a "write about these times when you tested a machine learning application" card to the backlog for this blog. I wonder if I'll get around to writing that, since it would be hard to explain it better than Bill did that day. He talked about how training data reinforces stereotypes, and how understanding the domain is crucial to determining what's a random failure vs. what's a systematic failure. 

Louise Gibbs gave a talk on starting her automation journey with a record and playback tool. That's also what got me excited about automation originally, and I'm etnerally grateful to have had the right people steer me towards tests at a lower application level before UI auomation became the only tool in my toolbelt. 

Suman Bala's introduction to Charles Proxy was a memorable one. She'd hooked up her phone to the projected screen without turning her notifications off, so we got to see all the tweets streaming in in real time! If you're just diving into Charles Proxy, the [recording of this talk](https://www.ministryoftesting.com/dojo/lessons/breaking-boundaries-using-charles-suman-bala) is a great place to start. 

Dominic Kua's talk on bash commands, Wim Selles's talk on Appium, and Henrik Stene's talks on consumer-driven contracts definitely fell into the "these people really know their tool" category. If they were tools I was using, I'd certainly consult their tips and advice. 

Emily Bache's talk shared the ideas from the State of DevOps reports and ultimately the Accelerate book. As a team lead and co-host for a testing ensemble, I was able to help empower people across teams and help build a culture of psychological safety. In my new role as Quality Lead, I'm just starting to collect the DORA metrics to help me decide where I should focus my efforts within the department. 

---

What a memorable group of people, location, and journey it was to TestBash Manchester 2019. I hope the [upcoming TestBash UK](https://www.ministryoftesting.com/news/testbash-brighton-2022-cancellation-and-testbash-uk) is in the cards for me this coming year, and not only because I still dream about [this Indian food](https://www.mowglistreetfood.com/) I had on the way in and out of Manchester.
