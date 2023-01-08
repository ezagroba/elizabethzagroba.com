.. title: Building Skills Over Time
.. date: 30 December 2022
.. tags: communication, leadership, humans, mindset
.. previewimage: /images/posts/2022/butterfly.jpg
.. description: Holding learning sessions to get everyone up-to-speed.

Our engineering teams have developers and testers on them. For our other roles, we've got specialists shared across teams: product owners, UX designers, UX researchers, data analysts, technical writers, etc. Specialists usually attend the weekly refinement sessions and sprint reviews, and skip the other sprint ceremonies.

One of our engineering teams is adding a Kafka event-driven architecture to our low-code platform. One of the specialists serving the team was struggling to understand the atomic particle of this architecture: business events. (Here's [my favorite concise introduction to the topic](https://www.gentlydownthe.stream/).) They kept thinking in terms of a user interface, while the team described a back-end system. 

I saw the specialist struggling in meetings as patient subject matter experts used their lingo to explain it all. The specialist still seemed lost. I met with them individually and realized why they were stuck in the UI: they didn't know how APIs worked.

## I don't know how APIs work.

All the explanations from our subject matter experts had jumped from "a user does this" to "so an API does that", but this specialist didn't have a good grasp of what an API was. Any explanation that started with "you don't want the API to be tightly-coupled" did not sink in for them. Explaining it more times wasn't getting them there. We needed to start from the beginning. 

I say "we", because as Quality Lead for the department, I see my role as making everyone else's work smooth and shiny. I also suspected this specialist wasn't the only one struggling with the topic.

## Let's learn together.

I started scheduling optional 45-minute meetings every few weeks. I didn't have the energy to add another weekly or bi-weekly recurring meeting to my slue of calendar invitations. Ad-hoc one-by-one sessions made this endeavor manageable and opt-out-at-any-time-able.

For topics, I saw that there were a few steps I knew we should cover to get everyone up-to-speed on business events (and how they're talked about in the context of our product and company): 

1. What is a REST API?
2. What is an OData API? 
3. When would you choose REST over OData or vice versa?
4. What is a business event?
5. When would you choose business events over/combine them with REST or OData?

I kept all the details in the same Dropbox Paper document: 

- the ultimate goal (to understand when to use business events)
- upcoming potential topics (starting with the list above, which grew as bigger questions came up during the sessions)
- the date and specific topic for the next session (we'd decide at the end of each session what the next most important step was)
- the recording of the Zoom call from the session
- the notes I took during the session

Yes, I took notes in addition to recording the sessions. Every session, I'd share my screen and take notes. My intention was specifically to help others learn, so recording the sessions _and_ taking notes (that they could help clarify and correct in real-time) freed them from the cognitive load of both learning and remembering in the moment. 

For the earlier sessions when I was explaining the topic, taking notes helped slow me down enough for the information to sink in for people who were hearing it for the first time. The notes provided an obvious place to collect links with examples of API specs or tools (like [Postman](https://www.postman.com/) and [the OpenAPI web editor](https://editor.swagger.io/)). 

For the later sessions when the subject matter experts were explaining the topic, the notes helped me make sure I'd understood what was said and capture the answers to questions from the audience. 

The notes also served another purpose later: it helped people decide if they needed to watch the recording. The extended team I invited to these sessions was seven people, and later two subject matter experts, so not everyone could make a 45-minute meeting fit in their schedule. People who can't take 45 minutes to learn something crucial about their work really don't need to spend 45 minutes watching a video to find out if they care about a topic. Glancing through the notes helped them decide if they wanted to hear the whole conversation. 

## Impact one year later

In the first few months, some people were learning and some people were listening to information they already had a good grasp of. It took a few months for everyone to be learning. That's when these sessions really started to pay off. Even if I felt like they'd been rambling, obvious, or useless, one of the seven participants would reach out to me to confirm that the session and the notes helped them. That feedback kept me going. 

At the retro the Kafka team had looking back at 2022, there was a stickie about this specialist. It said that collaboration between them and the team had improved. I had to agree. They shared a common vocabulary. The specialist understood the concepts the team was dealing with. They could conceptualize beyond the UI to the back-end. The team goes to the specialist for little/quick quick questions in a way they wouldn't have before, because every conversation felt like starting from the beginning. Now, they hit the ground running, together. 

I also want to give credit to this specialist: their remarkable improvement reflects the overall time and effort they've put into deepening their knowledge on business events. The sessions I organized were only part of their journey.

## Takeaways

I think most of our specialists had enough of an idea about REST APIs when we started these learning sessions a year ago. But nobody knew as much about REST, OData, business events, and how or why to combine them as they do now. 

I started with the belief that if one specialist didn't know everything, likely other people were in the same position. I had a growth mindset for my colleagues: given the right environment and the right pace, all of these specialists could absorb this information. I also had a growth mindset for myself: given enough time, I could make a difference. It was worth the investment.

![](/images/posts/2022/butterfly.jpg 'Photo by <a href="https://unsplash.com/@scw1217">Suzanne D. Williams</a> on <a href="https://unsplash.com/photos/VMKBFR6r_jg">Unsplash</a>')


