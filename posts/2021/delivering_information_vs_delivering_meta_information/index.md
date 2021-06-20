.. title: Delivering Information vs. Delivering Meta-Information
.. date: 20 June 2021
.. tags: testing, mindset, communication, leadership
.. previewimage: /images/posts/2021/victor-garcia-unsplash.jpeg

One of the first testing skills I built was [bug reporting](https://elizabethzagroba.com/posts/2014/2014-02-24_writing-clear-and-effective-bug-reports/). I practiced narrowing down the steps to reproduce. I told my developers what was happening now and what should happen instead. I learned to include where the issue was occurring, so my developers would stop closing my bugs with the `Works for me` resolution in Trac. 

In 2013, [Paul Holland](https://twitter.com/PaulHolland_TWN) taught me to tell the story of my testing. That is, meta-information about my testing. Sure, I still reported the outcomes: these things didn't work, these things did. But I also reported:

1. how I tested the product
1. how good that testing was

How long did it take me to test? What was difficult about my testing, made it difficult to get started, or slowed it down? What wasn't I able to test? The reason we tell those stories is to help uncover product risks, process risks, and get help from those around us to solve the issues. 

This is meta-information about my testing. It's what I'm seeing as I'm doing it, one level removed from the actual testing itself. (Look up `testopies` [testing + autopsy] for more on gathering meta-level information about your testing.) 

Building the skills around meta-information are important for doing any job well. These skills include:

1. identifying when you're communicating at the information level, or the meta-level
1. switching between and keep track of whether you're communicating at the information level or meta-level
1. naming the different levels, and bringing the people you're communicating with on this level-switching journey

These recent examples stick in my mind.

---

### Addresing the question vs. addressing the miscommunication

I was interviewing a candidate for a Software Development Manager position. For about a half hour, every question proceeded more or less like this:

1. I'd ask a question.
1. The candidate would speak for a minute or a few, without answering the question.
1. I'd rephrase the question, be more specific, or add more details to help the candidate understand the question[^1].
1. The candidate would speak again, again not answering the question.
1. I'd try once or twice more, before moving on to the next question. 

I realized early on that this was happening. I consider it an essential skill to be able to answer a question directly, or identify when you're having trouble doing that, as a Software Development Manager. I decided I'd reject the candidate, but realized I'd still have to get through the rest of this hour with them.

My colleague, my co-interviewer, took a different approach. He called out the miscommication problem to the candidate! He said "Elizabeth is asking you questions, and you're not answering them. Did you notice that? Why is that?" It was direct in a way that made me uncomfortable, and that I would have trouble doing with someone I just met. But he moved the conversation to where it needed to be: the meta-level. The candidate struggled to answer this question as well.

I jumped in to ease the awkwardness. I offered up my theory: the candidate's responses weren't answers, they were the candidate agreeing with the premise of the question. My colleague completely agreed, thanked me for contribution, but politely redirected the burden of this problem onto the candidate. The candidate continued to struggle without acknowledging the issue or the awkwardness for the rest of the interview. It was a clear decision for both me and my colleague: we would not be hiring this person.

### Difficulty scheduling a meeting vs. telling them that

I was asking for more details on the planning of a project in standup. My developer described how hard it was to find time with a particular developer on another team. They said the project was going to take weeks to scope instead of the days they thought it could take, if only they could find time with this person. The project seemed important, already had a deadline (or really, sadline[^2]), and waiting until the next free spot on this person's calendar wasn't working. 

I asked my developer "Have you given his this feedback directly?" I suspected that only the information had been communicated: the following meeting would have to wait a week. My hunch was correct. I suggested my developer try giving this person the meta-information: about how hard they were to schedule, how this was cutting into the time we had to work on the project once it was scoped, and how that threatened the deadline. Imagine how differently this person could react and rearrange what they were doing, or share their relative priorities so we could adjust our expectations, when given this meta-information. This was last week, so I don't know yet how this story ends!


### Adding testing details to the story vs. why I'm asking for them

There was a user story about being able to send metrics from our application to another application. I was picking up the testing on the story. My developer said they'd confirmed in the other application that our metrics were sent. They'd only sent a success, so I was planning on using the same setup as they did to look in the other application, but see what a failure looked like instead. 

But that's not what I told my developer. What I said to them was: "Add enough details to the ticket so I can test it." It turned out, we had different ideas about what `enough` meant. First they added a URL. I followed the URL and it went to a blank page with a header. I said the same thing again, "Add enough details to the ticket so I can test it." They wrote down the first button they had to click on. I asked a third time. They added one more detail, which still didn't tell me enough. But I got tired of asking. I tried all the options in the application, Googled to figure out what SQL query I needed, executed it, triggered a variety of different failures, and confirmed that they were received. 

Later, I explained to my developer the difference between my expectations and what they wrote. They explained how their expectations were also violated: they had to reach out to the team from the other product, figure out what to do, poke around in the product, and that the details they left me were all they received to be able to eventually figure it out. To them, just the URL going to a blank screen was `enough`[^3]. 

I realized then that I had left out a crucial piece of meta-information: the reason I was asking for the details. I wanted to skip that poking around time. I had ten other tasks this day, and expected this to only take 20 minutes instead of the few hours it ended up taking. I was hoping to benefit from the poking around work my developer had already done. I was expecting a lot of context, and my developer was expecting to only need to share a little bit of context.

Once I shared this with them, they understood where the gap was between my expectations and theirs. 

--- 

The suggestion about scheduling difficulties, that was an easy conversation to have. The other two were quite difficult for me. They took patient, active listening. I had to keep asking myself if I'd been clear enough with my expectations. They definitely made me sweat. 

Moving between information communication and meta-level communication is a skill. It takes time, failure, reflection, and practice to do it. Doing it well is a leadership skill. [_Crucial Conversations_](https://app.thestorygraph.com/books/b15fe452-5b8e-49f5-9e0b-90da490b944c) helped me identify when it's worth working on the relationship with a person and investing in these conversations. You don't have to be managing people (as I am currently) to be building or using this skill. 

What meta-level conversations are you avoiding? Are there people where you find you're only able to communicate on an information level? Have you tried communicating with them on a meta-level? What would happen if you told them that's what you were trying?

[^1]: In high-context cultures like the United States and the Netherlands, the deliverer assumes the burden of the miscommunication, not the receiver. There's more about this in [_The Culture Map_](https://app.thestorygraph.com/books/f0d396c1-fcd9-4beb-9538-4d11e04e3e1c).
[^2]: A deadline is when somebody dies. Most things we call deadlines at work are just sadlines, in that people are alive but just sad when they're missed. Read more about it in [Liz Keogh's blog post](https://lizkeogh.com/2017/08/31/reflecting-reality/).
[^3]: My colleague is coming from a low-context culture. I'm coming from a high-context culture. You can read more examples of this in [_The Culture Map_](https://app.thestorygraph.com/books/f0d396c1-fcd9-4beb-9538-4d11e04e3e1c), but it's the kind of non-fiction book that could have been a blog post, so just read the rest of this blog post instead?
