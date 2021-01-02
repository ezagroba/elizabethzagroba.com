.. title: SoCraTes UK, August 2020
.. date: 2 August 2020
.. tags: conference, testing, note-taking
.. previewimage: /images/posts/2020/hypergrowth.png

After years of envying the tweets and stories from SoCraTes conferences, this cursèd disease finally made attending one possible. I could afford the time (part of one day, instead of a whole weekend + travel) and the cost (£2.50, instead of €€€). 

I'm preparing to host an open space of our own in September ([TestCraftCamp](http://testcraftcamp.nl/), tickets are free!), so aside from the sessions, I was also interested in the infrastructure of the event. The hosts hung out in one central Zoom room (a one-month subscription cost them £10). Each attendee was appointed co-host, allowing us to move around among the many breakout rooms as we pleased. (There may have been as many breakout rooms as there were participants, named with varying levels of creativity but functionally the same.) A [Notion](https://www.notion.so/) board captured the user-generated schedule, along with links to the [Mural](https://www.mural.co/) whiteboards the organizers created for each room, rather than for each session. Chat happened in a [Discord](https://discord.com/) channel, but [I wouldn't recommend it](https://twitter.com/ezagroba/status/1287372791168278529). 

The first session I attended was a discussion about the value and hazards of leaving a job. First: decide where you want to go, what kind of thing you're looking for. You're not going to get where you want to go by running away from your current role. Run _towards_ something. Have honest conversations with your peers, manager, mentor, coach, etc. about what change you can affect at the organization. (Things like the nature of the product, the tech stack, or the customer base are unlikely to change quickly.) If you do decide to change jobs, it will take a lot of energy to find something new and build your network at the new place. You may have to prove yourself all over again, and solve the problems you've already solved with this different group of people. 

After taking a total of three bullet points in my notebook, the host of the second session I attended about hypergrowth was having trouble taking notes and listening to/facilitating the session. I volunteered to jump in to take the notes. Here's what I made:

![](/images/posts/2020/hypergrowth.png "Notes from hypergrowth session")

I was trying to capture what people said, change the background colors, and move the notes around to put similar ideas next to each other. It was hard to know in the moment whether all of that is legible or helpful for anyone else. Luckily people in the session and in the Discord channel later thanked me for my work. I'm still struggling with how to impart any note-taking skill onto others, particularly when this can be seen as a gendered task.

> Men: Wow, you are so good at taking notes!<br/>
> Me: You would be too if you got stuck being the one doing it all the time!

But I digress, back to hypergrowth: The things that worked before COVID and at smaller orgs don't work at a bigger org today. Find your people within the smaller org - your department, your mentor, your friends - so you can feel stable even as things around you grow and change. Communicate your expectations clearly, for yourself and for your team. Keep a journal of what you've accomplished to feel more anchored in the value of your work. 

After lunch, I started off in the wrong room because I didn't notice the sessions had been moved, but found my way to the one about coaching your peers. The conversation floated from a definition of terms to how to make space for mentoring. In order for people to mentor, there must be consent from the mentee. Ideally there is also some expertise in the organization around what is good, and someone (mentor or not) to teach the mentee what is good. The conversation reminded me of a talk I saw from Marianne Duijst; [here's the moment she started talking about the difference between coaches, sponsors, teachers, and role models, and how they can support you in different ways](https://youtu.be/vXIZpe-x4o8?t=595).

Anytime Maaret Pyhäjärvi is running an exploratory testing session, go to it. You will be better for it. This time, we tested a simple web application. We ended up spending most of the time adding scenarios to the automated tests Maaret had already set up in Robot framework. One of the questions it brought up for me: do you leave failed tests in your automation suite to highlight unexpected behavior? I had this problem this week: I'd updated a schema to validate against the current behavior while the story was in progress, instead of the behavior we wanted when it was done, so I could verify other fields in the output. Next time I think I'll separate them into two tests and leave them both as pending (marked as xfail in the pytest framework) so it's clear something needs to change before the software is released.

Thank you for the SoCraTes organizers for, as I learned a coach does, holding this space for us to examine ourselves and reflect. As someone who is much more fluent in emoji than GIF, I'm grateful to have won the hearts of the participants with this "letting the cat out of the bag" GIF in the GIF challenge.

![](https://media1.tenor.com/images/e49bc18b66056a71171ae6f16046a2a4/tenor.gif?itemid=11543319 "Cat aggressively jumping out of a backpack")