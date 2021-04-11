.. title: Recently Encountered Logical Fallacies
.. date: 31 March 2021
.. tags: testing, logic, critical-thinking, naming
.. previewimage: /images/posts/2021/statue.jpg

I was on [a panel about critical thinking for the Ministry of Testing](https://www.ministryoftesting.com/dojo/lessons/discussion-critical-thinking) last week. One of my fellow panelists and commendable ranter [Maaike Brinkoff](https://twitter.com/Maaikees) brought up *ad hominem* (personal) attacks as one example of a failure of critical thinking. It's one of many [logical fallacies](https://fallacyinlogic.com/) that are worth exploring further. 

Equipping yourself with the name for a thing helps you recognize it when it appears. (Lara Hogan wrote recently about applying the skill, of [being able to name the problem in the room](https://leaddev.com/communication-relationships/skill-naming-whats-happening-room), to defuse tense meetings.) These are some of the fallacies I've across recently when I've been debriefing testing sessions, facilitating refinement sessions, and reviewing conference submissions.

### Affirming the consequent

Affirming the consequent is applying a conditional without the conditionality, or assuming something happened because you see a result. 

1. If P (I run the pipeline) then Q (the latest build will be available on the test environment)
2. Q (the latest build is available on the test environment)
3. Therefore P (I ran the pipeline) 

 We can't assume the converse: if Q, then P. Just because the latest build is on the test environment doesn't mean I ran the pipeline. Maybe someone else ran the pipeline, or put the build there manually. Maybe there haven't been any changes since yesterday, and the build from yesterday is still the latest one.

### Fallacy of composition

This assumes that something that applies to one member of a class applies to them all.

1. Y is part of X (Stephanie is an admin user)
2. Y has property P (Stephanie can see this page)
3. X has property P (any admin user can see this page)

We can't assume that what's true for one member of a class applies to all of them. What happens if Stephanie can be assigned more than one role, a more restrictive/regular user role in addition to the admin role? Can she still see it? What if Stephanie being able to see the page has nothing to do with her status as an admin user?

### *Post hoc ergo propter hoc* (correlation without causation)

This one is easiest to see when others are debreifing their testing to me, but I've also learned to catch for myself. 

1. Event A occurred (I clicked the button)
2. Then event B occurred (a whole bunch of log messages appeared)
3. Therefore A caused B (clicking the button caused a whole bunch of log messages)

We can't assume that events that occur in a particular sequence in time are necessarily causal. Did clicking the button trigger the log messages? What do the log messages say? Did you read them? Who else could be using this environment? Does the same thing happen every time you click the button, or when you run the application in a different environment? 

### Argument from repetition

When someone says the same thing enough times, or brings up the same unimportant issue in a refinement meeting week after week, it can become easier to address the issue rather than convincing them yet again why it's not a priority. I've been facilitating refinement meetings every week for my teams for the past two years. [I only have a finite amount of energy](https://butyoudontlooksick.com/articles/written-by-christine/the-spoon-theory/) that is not always worth expending by refuting the case for a small edge case week after week. 

---
Shoutout to my logic professor Dan Cohen at Colby College, who had us memorize and distinguish logical fallacies as part of his brilliant Logic and Argumentation course, and pointing out that an ease and comfort with truth tables would translate well to a computer science course. Special thanks to Joep Schuurkes for his philosophical and technological opinions on this piece.