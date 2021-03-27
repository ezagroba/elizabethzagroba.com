.. title: Recently Encountered Logical Fallacies
.. date: 27 March 2021
.. tags: testing, logic, critical-thinking, naming
.. previewimage: /images/posts/2021/statue.jpg

I was on [a panel about critical thinking for the Ministry of Testing](https://www.ministryoftesting.com/dojo/lessons/discussion-critical-thinking) this week. One of my fellow panelists and commendable ranter [Maaike Brinkoff](https://twitter.com/Maaikees) brought up *ad hominem* (personal) attacks as one example of a failure of critical thinking. It's one of many [logical fallacies](http://www.fallacyfiles.org/) that are worth exploring further. Equipping yourself with the name for a thing helps you recognize it when it appears. ([Lara Hogan wrote recently about applying the skill, of being able to name the problem in the room, to defuse tense meetings](https://leaddev.com/communication-relationships/skill-naming-whats-happening-room).) These are some of the fallacies I've across recently when I've been debriefing testing sessions, facilitating refinement sessions, and reviewing submissions for Agile Testing Days.

### *Modus ponens* (affirming the consequent)

Yes, these problems are old enough to have Latin names. Affirming the consequent is applying a conditional without the conditionality. "If I run the pipeline, the latest build will be available on the test environment." If I go and look at the test environment and see the latest build there, I might assume the pipeline was run. But it could be that someone put the build there manually. 

### Fallacy of division

This assumes that something that applies to one member of a class applies to them all. "Stephanie is an admin user and can see this page. Therefore, all admin users can see this page." What happens if Stephanie can be assigned more than one role, a more restrictive/regular user role in addition to the admin page? Can she still see it?

### *Post hoc ergo propter hoc* (correlation without causation)

This one is easiest to see when others are debreifing their testing to me, but I've also learned to catch for myself. "On the test environment, I clicked the button, then a whole bunch of logs appeared." Did clicking the button trigger the log messages? What do the log messages say? Did you read them? Who else could be using the test environment? Does the same thing happen every time you click the button, or when you run the application locally? 

### Argument from repetition

When someone says the same thing enough times, or brings up the same unimportant issue in a refinement meeting week after week, it can become easier to address the issue than convincing them yet again why it's not a priority. I've been facilitating refinement meetings every week for my teams for the past two years. [I only have a finite amount of energy](https://butyoudontlooksick.com/articles/written-by-christine/the-spoon-theory/) that is not always worth expending by refuting the case for a small edge case week after week. 

---
Shoutout to my logic professor Dan Cohen at Colby College, who had us memorize and distinguish logical fallacies as part of his brilliant Logic and Argumentation course, and pointing out that an ease and comfort with truth tables would translate well to a computer science course. 