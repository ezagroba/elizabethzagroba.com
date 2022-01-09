.. title: Unblocking Your Test Strategy
.. date: 22 October 2021
.. tags: automation, coaching, testing, risk-based-testing
.. previewimage: /images/posts/2021/lightbulb.jpeg

In my new role as Quality Lead for my department, I get to figure out how to infuse everybody's work with "quality", and also figure out what that means exactly. 

One of my colleagues made it easy for me on my second day by coming with a relatively concrete problem: they wanted an acceptance environment for their team. Their team (henceforth: Eager Team) integrated with chronically overloaded and busy team (henceforth: Busy Team), so they wanted an environment where they could test their stuff together before it went into production. They wanted me to help set that up. 

I started my conversation with Eager Team Lead by taking one step back: why did they want this environment? They'd proposed a solution, but I wanted to spend at least a few minutes digging into the problem space with them to hear more about why they wanted this.

---

### Come up with dream scenario

I asked Eager Team Lead what their dream setup would be for their test automation, and why that was the dream.

Eager Team and Busy Team already had a test environment hooked up to one another. But they both threw whatever they were in the middle of on that environment. Eager Team couldn't count on a stable, usable version of Busy Team's software, and vice versa. Eager Team wanted a place to see what would happen against the production version of Busy Team's code. They wanted to automate all the things they could, and have a place to run that automation. 

### Identify (and confirm they are indeed) constraints

Unfortunately Busy Team was busy. They wouldn't be able to make setting up an environment for Eager Team a priority in the next few months. I had that impression, and so did Eager Team Lead. They were, after all, Busy Team. But I wanted to make sure that the busyness of Busy Team was a constraint. I took on the action point to follow up with Boss Person about how we could both (1) check that Busy Team was indeed too busy, and (2) how to get this request on Busy Team's long list for the future.

I also dispelled one of assumptions underlying Eager Team Lead's dream setup: it was important to test everything, in an automated way, in the ideal environment, or else testing wouldn't be valuable. I explained that it's [impossible to test everything](https://app.thestorygraph.com/books/8ba29269-1843-4ac1-be0c-226752b17937). Testing in an automated way would be more likely to reveal known unknowns than the unknown unknowns their team was interested in. And that it wasn't all-or-nothing - every little bit would help.

### Choose achieveable pieces within constraints 

Rather than killing the dream, I identified a valuable first step in the direction of the dream. Eager Team would write down, in English to start, 3-5 things that they want to test using both their software and Busy Team's. They'd show those to their product owner to make sure they were things customers cared about. From there, we could look at whether to build automation, and if so, where to run it. There was that test environment already. We had production, could we use feature flags? Could we keep the data only visible to our employees internally? 

I knew I'd hit a nerve when Eager Team Lead said "Oh, we can just start iterating over this!" Because of course, the software itself is not the only thing you can build in an iterative way. Your test automation can also mitigate risk, confirm assumptions, and provide value along the way. 

---

So how'd it go? I confirmed Busy Team's busyness, and got more details on how and when to add this request to their list. I'm following up with Eager Team next week to see where they are in identifying valuable scenarios, or if I should jump in there too. 

But wow, what a feeling to be able to lift the weight of "I need a thing I don't know how to build and don't think I can ever get" off someone's shoulders and replace it with "I know what to do next and it's achievable." 

Stay tuned for more quality leading to come.