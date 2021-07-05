.. title: Complete the Main Quest First
.. date: 4 July 2021
.. tags: critical-thinking, reporting, testing, risk-based-testing, mindset, exploratory-testing, charters

Recently, I made an outline for a tester (who was still onboarding) for what kinds of things to test on a new API endpoint we added. They explored, wrote a bunch of automated tests to capture their work, and came back with a list of interesting and good catches in the error responses. My first question in our debrief was: did you try a successful response? They hadn't. I sent them back to tackle that too. 

Because a successful response is the first thing our product owner is going to ask about. That's what we'd want to show off at the review meeting internally to demonstrate the new API endpoint. That's the first the customer is going to try. They're going to copy the request from our OpenAPI specification, paste it in Postman (or the tool of their choice, but our customers so far have been using Postman), and see if their credentials will get them the response that matches the specification. These stakeholders share a common concern, and that's the risk we should be migitating with testing. First. 

## Complete the main quest first.

Complete the main quest first. Come back to the side quests. 

A customer had asked for this API endpoint to be added. If we'd tested the happy path first, we would have had the option of releasing the API for the customer to use. The risk of discovering a successful request wouldn't yield a successful response was relatively low in this case, since our developers tend to try one happy path themselves.

But what if the main quest had required a lot of setup, explanations to build knowledge and context for the onboarding tester, or yielded an issue? I'd done a risk-based analysis of what all to complete as part of our definition of done for this story. But I hadn't shared my approach to completing the main quest first, so the tester did what testers do, and went on a hunt to find weird stuff. 

![](/images/posts/2021/iceland.jpg)

## Note down and follow-up on werid stuff; do not get distracted by it

Software will break in all sorts of ways. The more time and curiosity you have to dig into it, the more you'll discover. But are those the most important things? 

In this API, the tester discovered that if you paste 10,000 characters into a field that's meant for a UUID, you get a 400 response. But did they try a regular old UUID first? What if they get a 400 response no matter what they put in that field, because the field name in the specification doesn't match what's in the code? Is trying 10,000 characters the first and biggest risk they have to face when presenting this API to a customer?

I'm not saying don't try 10,000 characters. [I love that shit](https://twitter.com/ezagroba/status/1234822805709053953). But decide if it's a risk you care about first. [If you don't care about the outcome, don't test it](https://elizabethzagroba.com/posts/2020/2020-05-24_if_a_test_falls_in_a_forest/). Don't make busy-work for yourself just to fill the time. 

## Make side quests a concious choice

Before you start throwing 10,000 characters at your API, talk to your team. Your developer can probably tell you if they never built something to deal with that situation. Your product owner can tell you they'd rather have it to the customer sooner. Your data analyst can tell you if there's already longer stuff than that in the database, or if you should be trying Japanese instead. 

Make side quests a deliberate choice. Share them to increase their value or figure out who on the team is best-suited to execute them. 

## Recognize when the quest is a journey, not a destination

Throwing 10,000 characters at an API may be a way to start a discussion about the speed at which responses are returned. It might be a way of showing [your favorite random text generator](http://coffeeipsum.com/) to your fellow tester. It might be an exercise at an ensemble testing session, where everyone can practice pausing before executing an idea to describe the expected behavior first. 

Quests can be valuable in ways that are not directly related to the finishing the quest. 

_Note: I got asked recently if I use the word charter much with non-testers. I don't. Try reading this again but replacing every mention of "quest" with "charter"._