.. title: Anarchist Software Architecture
.. date: 10 April 2023
.. description: Design systems without blocking the work.
.. tags: system, architecture, dependencies

An Assertive Tester at work sent me a direct message declaring that the two of us should decide which repository the tests should go into. They'd decided we were "the deciders" here since they saw themselves as the highest-ranking tester in their department, as I am in mine. 

For most technologies, it makes sense to host the tests in the same repository as the code. For a variety of very good reasons I'll go into below, the API and browser-level tests for our apps are all hosted in one big, shared repository. Older browser tests were using Selenium, but some teams had started to move towards using Playwright. 

The Assertive Tester wanted to decide if new Playwright tests should join the existing tests in the big, shared repository with the other tests, or exist in their own git repositories until the apps themselves could be moved to git. They set a meeting with me for a few days later. 

## Invite your comrades

I wasn't in the unit where most of these teams using the big, shared repo were. I didn't know their day-to-day struggles, or even if the tests in the repo were still being run. 

I reminded the Assertive Tester that I wasn't an expert in everyone's context, and asked them if it would be all right if I invited the people who write tests for other teams. The Assertive Tester agreed, if reluctantly. 

## Ask them for their context

I posted in the Slack channel we have for the members of the big shared testing repo, inviting them to the gathering in a few days. In the thread beneath the message (mistake here, I should have made the more visible message in the channel include all my questions), I asked them to thread their response to a few questions, whether or not they could join the conversation. The questions were:

>
1\. Is your project hosted in our legacy version-control system or gitlab?<br/>
2\. What are you using for browser automation now?<br/>
3\. Is collaboration across teams important for your testing framework?

The day before the gathering, I followed up in the Slack channels of invididual teams to find out about their browser tests. 

## Give them sufficient context

Then I started a document. Initially, it was to collect the responses to those three questions that were now scattered across a few channels. I collected them in an orderly table. I later added a couple sections at the top to make sure the gathering could be contained within the hour as scheduled. I listed what I knew about the situation for the first few years that the big shared testing repo was used:

>
1\. Tests couldn't be stored in the same place as our apps. <br/>
2\. Code for login, API tokens, things all our apps would need were maintained by one team.<br/>
3\. We all worked in the same unit, sat near each other, and collaborated in an ensemble to write browser automation code together.

## Gather to discuss

The Assertive Tester kicked off the meeting before handing it to me give a brief history. I gave a summary of the history and questions for our consideration. Then we went around to each participant to confirm the  details in the table and find out if there was more to the story. The discussion led us to two more salient points in our history:

>
4\. We required merge requests to be approved by the one maintainer, and later one of four maintainers. <br/>
5\. We wanted people to learn Python as part of their skill set.

And several more points for our consideration:

>
6\. The Assertive Tester found the .gitlab-ci.yml for the big shared testing repo was too complicated when it contains both Selenium and Playwright. (Finally, I discovered the motivating reason for this discussion!)<br/>
7\. Teams like being autonomous! The team (not just the tester) should own the test automation code.<br/>
8\. Do we want to teach/enforce how to write tests in a certain way? Would it help people to onboard and quickly use a more shared testing framework?<br/>
9\. The big shared testing repo has too many files to navigate easily. It's hard to convince developers to use it. 

Only point 6 reflects the earlier point in the discussion I captured before a conclusion was reached: we don't need to optimize for people moving between teams because it happens so rarely. 

Looking at the table of who was using what: 

- some teams had their app code still in our legacy version-control system
- some of those teams had abandoned the big shared testing repo and had their own gitlab repos for their Playwright tests
- some teams were using frameworks other than Selenium or Playwright for their tests (we added a section to capture those pros and cons)
- some teams weren't testing things in a browser 

No two teams of the nine total were in the same situation. With most of the history for one big shared repo no longer applicable, the desire for developer collaboration within teams over tester collaboration across teams, and a relatively easy setup time for authentication, we decided each team should host their own tests. And when possible, put them in the same git repo as the application code. 

## Write things down

With the exception of point 6, the rest of these points above are captured as facts. I appointed myself note-taker and screen-sharer for this conversation. I wrote down the questions we discussed as they were introduced, and overwrote them with the answers as we decided on them. At the bottom of the document (though I should have put it at the top), I added a `Decision` section. It's very short: one sentence and three bullet points linking to repositories. The sentence is: `Let's not share a repo for all of the tests.` 

Captured in this way, anyone could glance through this document, understood what we talked about, determine who was involved in the decision-making, and see how we came to the conclusions we did without having to watch the whole Zoom recording of the meeting. 

---

Why am I telling you this? Because I discovered this kind of high-level decision across teams has a name: architecture. I made an architectural decision about the tests in teams around the company! Well, not exactly that, even better: I brought together the forces that made the decision become clear. 

At [BoosterConf](https://boosterconf.no/) recently, I met [Andrew Harmel-Law](https://twit.social/@ahl) and saw his talk called "A Commune in the Ivory Tower: A New Approach to Architecture." He is literally writing the book on anarchist decision-making in software. (He came to my open-space session about job titles after I introduced myself as an organizational anarchist. Hurrah for outside-the-box labels!) 

You should really watch [his whole talk](https://2023.boosterconf.no/program/friday/5_short_talks/kongesal_1/). It was how I discovered I was doing architecture, but in a decentralized, non-blocking, pulling, parallelizable fashion that didn't require a consensus. The document I create to prepare for and capture notes for that meeting serves as an architectural decision record for the big shared testing repo. I consulted the affected parties and offered advice (that teams can happily ignore) without getting in the way of their work. 

Andrew also happened upon this process himself as a way of not being the architect-as-bottleneck on projects. As these things go, he also discovered that this had already been discovered by [Ruth Malan](https://mastodon.social/@RuthMalan).

That's the whole story for today. I'm planning on reading more about anarchy and thinking about how it can influence my work, or possibly already does. For now, go forth and become anarchist architects! 