.. title: You Don't Have To Call It A Bug
.. date: 21 November 2023
.. description: Asking a developer to build a new feature got better results than asking them to fix a bug.
.. tags: communication, testing, naming, feedback
.. previewimage: /images/posts/2023/caterpillar.jpg

## The situation

In 2015, I was on a large team working to skin the pages of a Drupal content management system (CMS). I'd tested a Django CMS before, but Django is built on Python. Drupal runs on PHP. Every error page I triggered was an exciting new adventure of digging into what the problem might be, and which of the ~15 developers I should bring the problem to. All but one of them hadn't worked with Drupal before either.

Half of the team worked out of the office in Brooklyn, New York. The other half of the team worked out of the office in Bogotá, Colombia. Our main coordination meeting with the whole team was the standup meeting in the morning. Each group piled into a conference room. Most of us would get a chance to yell towards the microphone across the long table, strain to hear our colleagues in the other hemisphere doing the same. The unlucky ones only got to do the latter, until another project kicked us out of the meeting room. 

Imagine how well we communicated and trusted each other in such an environment.

## The perspectives

Imagine now, you're a developer on the team in Colombia. Elizabeth in New York has found a problem, and she thinks it's a bug. She found it testing your story, but you don't know enough about the system to know if it's even your problem. There are 14 other developers on the team, and any one of them could have caused it.

Imagine now, you're my boss, in charge of testers on several different projects around the company. You're trying to look at Jira to get some insight into my work. You do a search for "Bugs created by Elizabeth in the past two weeks."[^1] You are surprised to discover that Elizabeth seemingly hasn't found any bugs in the past two weeks. 

## The conversation, and my perspective

My boss came to talk to me. They asked why I hadn't found any bugs. Surely with a project as late and over-budget as ours, it must be ripe with bugs?

I had found bugs. But I didn't mark them as type Bug in Jira. I filed them as feature requests. 

I'd noticed that any Bug I filed came with hours of back-and-forth about whether it was a bug, whose problem it was, and a fight about whether the application behavior should change at all. Any Feature Request I filed was eagerly picked up and built in the time a Bug fight would have taken. 

The issues themselves were phrased nearly identically:

- Bug report I didn't file: When I go to the detail page from the list view, I get a 500 error. Instead, I should get the details that correspond to the title I saw in the list view.
- Feature request I did file: When I go to the detail page from the list view, I should get the details that correspond to the title I saw in the list view.

Same idea. Same code change. Different issues type in Jira. Why? 

Feature requests had story points. A developer who implemented a feature request had created something we needed where it wasn't before. At the end of the sprint, the number of points delivered by each developer could be tabulated in Jira. (I don't believe this was tied to compensation, but measureable outputs in Jira -- as evidenced by my boss's inquiry -- did seem to be a social currency at the company.) 

Bugs did not have story points. A developer fixing a bug would have completed fewer story points at the end of the sprint. They would also have to scream into a conference room microphone at standup the next day about how they couldn't pick up any new story because they were fixing a bug of their own making. 

My boss reacted to my explanation by simply switching their Jira filter from "Bugs created by Elizabeth in the past two weeks" to "Feature requests created by Elizabeth in the past two weeks." 

With the power of hindsight, there's a lot more I could have dug into about a culture that uses numbers from Jira as currency. Regardless, I do think this experience made me a better, more collaborative tester focused not on getting the credit/being right/finding the most bugs, but on getting the application fixed. 

## Lessons learned

I like to think back on my time at this company as my fastest learning experience. But when I was in the thick of it, all I knew I had learned from this experience is:

- Jira does not tell the whole story. 
- Approaching a situation with curiosity or excitement will get you a better outcome than approaching it as a fight.
- Getting the bug fixed is more important than labelling it as a bug.
- Keeping the lines of communication open to be able to deliver a message might be more important than any particular message. 

What political games have you played in order to get things done? When have you sacrificed credit or acknowledgement for progress? What's a worse metric to track in Jira to pit developers against each other than story points? 

---

> The way to get things done is not to mind who gets the credit of doing them.<br/>~ [Some dude](https://quoteinvestigator.com/2010/12/21/doing-good-selfless/)

---

![](/images/posts/2023/caterpillar.jpg "Bug, or feature request?<br/>Photo by <a href='https://unsplash.com/@timothycdykes'>Timothy Dykes</a> on <a href='https://unsplash.com/photos/macro-photography-of-green-black-and-gray-striped-caterpillar-A6-kVKvD5fg'>Unsplash</a>")

[^1]: At the time, I could have dictated the exact JQL (Jira query language) you'd need for this advanced search filter. I have nothing but gratitude for the brain space that forgetting this minutae has freed up. 
