.. title: Not Every Detail Matters
.. date: 12 February 2022
.. tags: testing, mindset, risk-based-testing, coaching

I was looking at a user story for one of the teams I support. The story was about improving a very particular page. Our users do see it. But only for 5-10 minutes per week, if they've started their work early. We deploy this product weekly just before working hours. Deploying currently involves taking the whole product down. Customers can sign up for noticifications so they're reminded about this downtime window. 

The story was to improve the look of a page. People might see it and be confused if the stars aligned and:

- They started work early.
- They hadn't signed up for the notification.
- They hadn't seen the web app with just a logo on it before.
- They didn't try it again in a few minutes. 

So I asked the ticket writer, "This doesn't impact customers much (5-10 minutes per week). Is fixing this worth the effort?"

They wrote back "I believe in 'Every detail matters.' This particular detail should take very little effort to realize, so my answer on this question is Yes."

It's possible they're right to pick this ticket up. It was a small enough effort that we might as well do it. If they're wrong, they're the one feeling the pain of explaining the ticket to the team, verifying the fix, deciding what to put in the release notes, etc. It's a safe-to-fail experiment for me as a quality coach. 

But I didn't have the same mindset. I don't believe that we should fix everything we find in our app that violates my expectations. I don't think it's possible to identify one correct set of expectations and priorities that our users will share. I don't think the things that we've already fixed will stay fixed. I don't think it's possible to cover every issue with an automated test. 

I think we need to let go. We need to decide what's important, and focus on that. The details of the downtime page -- the new design, and the time the team spent updating it, and the effort I'd spend having the conversation about it -- none of them mattered too much to me. We need to notice details, and also know when to turn our brains off to being bothered by them. We need to think about the risks of our tests could uncover; our goal isn't 100% test coverage. In short:

> Not every detail matters.

We are limited by our attention, energy, health, meetings on our schedule, time left on this earth. Software is complex enough that it's very unlikely we'll be able to solve every issue we find. The more time we spend solving the unimportant ones, the less time we have left to look for the important ones. Or decide what is important. Or understand our users better to be able to more effectively evaluate the relative importance of such issues. 

Jerry Weinberg cheekily noted the impossibility of this endeavor in his book accurately titled [_Perfect Software and Other Illusions About Testing_](https://app.thestorygraph.com/books/8ba29269-1843-4ac1-be0c-226752b17937). The Black Box Software Testing Course on Test Design emphasized the need for testers to balance risk vs. coverage. Its focus on [scenario testing](https://www.developsense.com/blog/2010/05/why-we-do-scenario-testing/) insisted we tie our testing to a user's journey through the software that was:

- coherent
- credible
- motivating
- complex
- easy to evaluate

I know this is the right approach. It will leave time to build new features and learn new skills. It's what will make it possible for us to feel fulfilled and motivated in our work. 

Now I just need to figure out how to scale this mindset. 
