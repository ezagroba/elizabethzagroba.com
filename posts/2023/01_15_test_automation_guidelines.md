.. title: Test Automation Guidelines
.. date: 15 January 2023
.. description: "Review this from a test automation perspective" they said, so I articulated my perspective.

I received a large merge request recently, with thousands of lines of code changed and a handful of bullet points explaining some of how the test automation framework had changed. "It's already been reviewed from a technical perspective," the author of the code said. "I'd like you to review it from a test automation perspective."

I'd spent a few hours dipping into the code and deciding how to approach this review. This "test automation perspective" charter came from [the conversation I decided to start with the author, before leaving any written comments on the merge request](https://elizabethzagroba.com/posts/2022/02_27_strengthen_your_code_review_skills/). I was looking to focus my efforts in a fruitful, productive direction, where my suggestions would likely be heeded. But what _were_ the test automation principles I should be evaluating against? What did I expect from the setup of a test automation framework? Which criteria was I using to evaluate this merge request in front of me?

The [Automation in Testing TRIMS heuristic](https://automationintesting.com/2019/08/trims-automation-in-testing-strategy.html) came first to my mind:

- Targeted
- Reliable
- Informative
- Maintainable
- Speedy

But there were other things I was noticing in reading the tests that made me question and identify my assumptions. I realized I needed to write down my assumptions. I wanted to come to a common understanding with the other testers in my department, rather than making decisions case-by-case, line-by-line with this author. 

And thus, the Test Automation Guidelines for my department were born. Or rather, compiled from years of working on test automation code and hearing greater automators than I am write and speak about the topic. 

___

## Test Automation Guidelines

### Entire repository

- Test automation code must be version-controlled and linted.
- Each function or method should do one thing and one thing only. Group functions and methods that do similar things together. “Separation of concerns” is usually how this is described.
- Code comments shouldn't duplicate information the code can provide. They should describe why the code is the way it is, and be used sparingly. 
- The README should contain information on setting people up who are new to the repository to run the tests, and information about code style and contribution guidelines.

### Individual automated tests

#### To automate a test or not to automate a test

- Tests should be automated to the extent that the effort in writing and maintaining them is less (or less frustrating) than testing the same thing through exploration. 
- Automated tests contain an assert or verify. Assertions are better when they are checking something unique (an id, a name, etc.). 
- If you're using automation to expedite exploratory testing and not decide something on its own, make that clear. 
- Each test should test one thing and one thing only.

#### Readability and ownership

- Tests should be readable. The best way to make sure you are not the only person who can read them is to pair to write them. The next best way is through code review. Smaller branches are easier to review and merge than bigger ones.
- Automated tests are owned by the whole team. 
- Automated test output should be readable. You should be able to tell from the output what the test was trying to do, and how far it got.

#### Determinism 

- Don’t trust an automated test you haven’t seen fail. If you can’t change something about the test to make it fail, maybe it’s not testing what you think it’s testing.
- Automated tests should provide information we care about. A big pile of green tests only helps us if they’re testing something relevant.
- A failing (or even worse, sometimes failing) automated test should be a problem. Invest the time to make it deterministic, or delete it. Run the tests and publish the results so failing tests matter. 

## Resources

1. João Proença’s talk: “[Should we just... delete it?!](https://www.youtube.com/watch?v=kEaAoSeQYNc)”
2. Joep Schuurkes’s blog post: [Test automation - five questions leading to five heuristics](https://smallsheds.garden/blog/2015/test-automation-five-questions-leading-to-five-heuristics/) 
3. Joep Schuurkes’s blog post: [How this tester writes code](https://smallsheds.garden/blog/2019/how-this-tester-writes-code/)

---

Another department at my company had collected the TRIMS heuristic and a few other pointers (automated at the lowest level, use static analysis tools, etc.) that I linked my colleagues to rather than rewriting. Outfitted with my guidelines and theirs, I was able to go from a conversation-as-code-review deeper into the line-by-line-is-this-what-we-want-here code review. 

I encouraged the author to identify and write down their own approach to the code after our conversation. They had strong opinions about what should go in a page object, when it made sense to break a test into more than one, and how the output should read when a test failed. By writing those preferences down, I could evaluate whether they were being applied consistently. Everybody needs an editor.

---

Do you have guidelines you refer to when reviewing test automation code? Beyond the links I provided above, is there some other reference you'd point me to? When do you find yourself bending or questioning the guidelines you thought you held dear?