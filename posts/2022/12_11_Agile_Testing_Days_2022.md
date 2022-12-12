.. title: Agile Testing Days 2022
.. date: 12 December 2022
.. tags: conference, agile-testing-days
.. previewimage: /images/posts/2022/sansoucci.jpg
.. description: Connecting with my peers again in Potsdam.

I was on the program committee for Agile Testing Days again this year, so I reviewed (anonymously) one out of every six submitted presentations. It was a bit heartbreaking to see the number of skilled professionals whose talks and workshops didn't make the cut. I can't say that the cutthroat competition necessarily led to a better program, but the sessions I attended surpassed my expectations. 

Agile Testing Days is A LOT, so these are my notes and takeaways from only some of the sessions I attended.

## Anne-Marie Charrett - Quality Coaching Masterclass

Anne-Marie graciously let me participate in (and host a small bit of) her tutorial about quality coaching. It was great to spend a whole day talking about and with people taking the same approach to their influencing without managing role. It confirmed that I've approached my role in a sensible way: have a mandate from management, wait until teams ask for help instead of inflicting help, give people an indication of when you'll come back for more support or follow-up, treat teams at different maturity stages differently. 

I need to revisit all the diagrams and lists Anne-Marie shared of what quality coaching can be. I want to look through each one and see if it's something I want to do more (or less) of as part of my role. "Investing in onbaording is the ultimate shift-left" is now my go-to explanation for why I'm spending so much time explaining stuff to the new joiners. 

## Gwen Diagram - Happiness is Quality

The little things (getting a PagerDuty call off-hours, flaky tests in the pipeline, a monstrous legacy code base) can pile up to drive your most talented engineers away and destroy engineer happiness. 

As acting CTO, Gwen measures *everything* at her organization. She tracks number of alerts. She hosts "flake parties" to finally fix or delete flaky tests. She uses (relatively infrequent every-two-months because nobody likes them) retros to collect all kinds of feedback. And crucially: to collect responses to the same set of questions over time. She knows that making every measure reflect 100% satisfaction is somewhere between not cost-effective and impossible, but she knows to keep "I am comfrotable asking for help" at 100%. 

## Fiona Charles - What could *possibly* go wrong?

Fiona covered a bevy of consequences of negligence, unethical practices, and misplaced confidence in software. Her particular example of testing the emergency services call system in England reminded me that I need to tie in the customer impact element more to the daily work of my teams. Agile is oriented to the people building the software, but not the people the software is ultimately inflicted upon. It is our responsibility as engineers[^1] to build software ethically, private, and secure by design.

[^1]:For more on this, I highly recommend [The Great Post Office Scandal](https://app.thestorygraph.com/books/1987d75f-ecb6-4a48-ad46-49cee7350c0c). It is jam-packed with WTFs per minute and will radicalize you on the issues of audit trails, release notes, and transparency for starters.

## Toyer Mamoojee - Refining your Test Automation approach in modern contexts

I'm glad I finally got to see Toyer speak after only hearing good things from my Agile Testing Days friends (arguably real friends now?) and the internet for years. Toyer revealed his depth of experience working in test automation through his lists of challenges he sees everywhere, and refinement guide to getting back on track. 

Everybody's got long-running tests, isolation issues, maintenance issues, lack of transparency, delays before testing, and a desire to tackle non-functional tests all at once. His refinement guide points to breaking steps down into smaller pieces: break a monolith into microservices, create a small and determistic test environment, write tests at the lowest level and closer to the code. Along with helping people build their automation skills, you've also got to shift their mindset to thinking about the ideal future state.

## Sam Nitsche - Trouble in the Old Republic

This is undoubtedly the most stagecraft I'd seen at a conference. Hell, I've seen plays with fewer lighting cues and costume changes. I didn't expect to also learn something at this talk after the smoke from the smoke machine faded, but remarkably, I did!

Database people have *really deep* knowledge about databases, but very little programming knowledge. They lack the fancy tools that developers have to perform their jobs more easily. Like Toyer suggested about automated tests, Sam recommended making the database part of the software. 

## Parveen Khan - Building Quality - Influence, Observability, and You

Parveen's in a position like I am, serving across several teams, and wondering if she's having any impact. She noted how much harder it is to build allies at work when you're remote. Setting up regular 1-on-1's to share accomplishments also builds trust and visibility for influence. 

For me, this list of knowing if you've influenced people was my biggest takeaway: 

- People come to you for your advice or your opinion.
- People do things for you when they don't have to.
- You can set a direction and move forward without authority. 

## Marie Drake - Learning the Fundamentals of Performance Testing

I've been on lots of projects that aspire but never execute performance testing. Marie's talk was a great introduction to and disambiguation of all the terms I've never seen executed: smoke, sanity, stress, spike, soak, and possibly other performance tests I couldn't write down fast enough. My biggest takeaway was: bottlenecks in the front-end happen for individual users, while bottlenecks in the back-end happen when there are too many concurrent users. 

Echoing what Gwen said in her talk: if you can't measure it, you can't improve it. 

## Ash Winter - Better organisation design enables great testing

Ash Winter's Golden Rules of consulting (what he blindly assumes before gathering any information) made me laugh, and definitely sound true:

- you have too much work in progress
- you are building stuff no one will use
- testing is not the real problem in your organization

The real problem is organizational design. Your org chart is not where the work happens; it's all the connections that you don't see and can't draw, built up through influence and reputation, that get stuff done. Discovering the shape of your organization can help you figure out what kind of testing you should be doing. (Maybe it's time to pick up _Team Toplogies_ again, although I hate that the authors tell you how to read it.)

## Laurie Sirois - Creating Career Ladder for QAs

Career ladders help retain talented engineers, align expectations, and hire more successfully. Nobody's career will be linear, but providing a structure for what the options are of what's next helps you give clear feedback to people about how they're doing. On the other hand, if your organization can't support people growing in their careers or has more T-shaped needs, a career ladder will be misleading and disappointing! 

---

It's amazing to me that conferences like this are part of the structure of my life. I live in a foreign country and work with very few people who have the time to help guide and provide feedback on my work. It's gathering with this community year after year that fills that gap for me. Thank you Agile Testing Days, Sansoucci Park, and the Dorint Hotel sauna. Thank you to Thomas Rinke, who thanked me for modelling how to ask a question and for banging on the piano a bit. Thanks to everyone who enjoyed [my real talk](https://agiletestingdays.com/2022/session/my-crafting-project-became-critical-infrastructure/), and [the talk that accidentally upstaged my real talk](https://twitter.com/BaileyHanna/status/1595500289653870593). 


![](/images/posts/2022/sansoucci.jpg 'Sansoucci Park in Potsdam')

And definitely no thanks for the projector in the main room or the Deutsche Bahn. 

