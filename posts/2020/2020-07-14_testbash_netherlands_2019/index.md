.. title: TestBash Netherlands 2019
.. date: 14 July 2020
.. tags: testing, conference, testbash

In reviewing my notes from the TestBash Netherlands that occurred in May of 2019, two big, related themes jump out at me: 

1. keep exploratory testing
2. learn by sharing

Andy Brown gave a talk about human factors in highly automated systems. As flying airplanes becomes more automated, pilots know less about how to switch to manual overrides in a time of crisis. You might not have more than a few hours a year of practice for when things go down. Continuing to share stories from the past and learn from them is one way out.

For [Gitte Ottosen](https://twitter.com/Godtesen), who gave us a tester's perspective on Agile, learning never ends. Understanding the customer journey and tying your work back to the business value are essential for making informed decisions about what to test, and which subset of those things to automate. Teaching, knowledge-sharing, coaching, and pairing can get the whole team involved in advancing quality, even if they're not all strong exploratory testers. 

[Jit Gosai](https://twitter.com/JitGo) spoke about continuous testing. Practice test-driven development, story mapping, and three amigos meetings before the code is written. Improve automation test suites, use exploratory and mob testing, and incorporate feedback from the customer. When you're exploratory testing, you're not just confirming that the software functions as expected, you're testing the goal of your whole organization. Jit found that getting everybody on the team exploratory testing caught more bugs than automated tests. 

[Marit van Dijk](https://twitter.com/MaritvanDijk77) hit the nail on the head with her talk: keep exploratory testing. Maintaining a consistent state of test data across mutliple teams is difficult. Rather than spend your time setting up control mechanisms for those systems, explore the systems themselves. Bugs are found not in the things we can control or know about, but in the space between systems. Pairing a developer with a tester was a lot faster than testing solo, because nobody had to go back and reproduce bugs. Spread the risk across systems by hooking them up one at a time.

[Vera Gehlen-Baum](https://twitter.com/VeraGeBa) and [Beren Van Daele](https://twitter.com/isleoftesting) spoke about incorporating your learning into your backlog. Identify what you want to learn, and write actionable acceptance criteria for your learning. This should include sharing what you've learned individually or with the team; it doesn't have to be confined to same sprint as the work for the team. Linking personal goals to business goals will ensure that people see they're improving.

[Joep Schuurkes](https://twitter.com/j19sch) talked us through what he was thinking as he was live-coding, which is learning and sharing at the most granular level. Separate concerns when you automate: keep what the code is supposed to accomplish separate from how it's accomplishing it. He expanded the CRUD heuristic that helps me decide what to automate, and added an extra DERR to make it CRUDDERR to ensure you can also debug, explore, run, and report on your code. 

[Anne Colder](https://twitter.com/Annosofie) and [Vincent Wijnen](https://twitter.com/VinWijNL) gave an experience report about their mentor-mentee relationship. Mentoring is different from teaching. Ask questions about your mentee's experience, and expect different questions from them than you'd receive from your more experienced colleagues. Mentoring stimulates reflection on both sides. 

Drew Pontikis spoke about the illusion of control. Challenge your own thinking by listening to new voices. Recognize when you can affect change in a situation.

[Ben Simo](https://twitter.com/QualityFrog) gave the last talk of the day about the art of scientific investigation. Design your next experiment based on your previous ones, and adapt as you go along. 

There was a whole slew of 99-second talks, but the only memorable and explicable thing I wrote down from them was something Ilena said: "Understand your team doesn't function the way that you do." 

The day prior to the day of talks, I helped facilitate and debrief a workshop that Joep Schuurkes developed around building an API testing framework. It was the first time we'd given it together, so that whole day was a 'learn by sharing' experience for me.