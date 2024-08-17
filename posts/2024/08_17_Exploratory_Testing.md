.. title: Exploratory Testing
.. date: 17 August 2024
.. description: Wander with a purpose, balance risk and coverage, no jargon
.. tags: exploratory-testing, testing, risk-based-testing, critical-thinking
.. previewimage: 

## What is exploratory testing?

There is always [more that can be tested than you have time for](https://vimeo.com/275859034). A tester’s mission is to best choose where and how to spend their time.

- wandering - purpose = lost
- wandering + purpose = exploring
- exploring + judgment = exploratory testing

Exploratory testing allows the tester to balance risk (the consequences of a failure) and coverage (observing all possible behaviors). It brings test design and execution together: you use the information you’ve gathered so far to immediately change what you’re going to do next.

## How does exploratory testing fit in with automated tests?

The code in automated tests tell you what’s expected (at the time the test was written, by the person who wrote it). The output from the automated tests tells you what you got (at the time the test was run, to the person paying attention to the output).

Automated tests can’t do the evaluation work to tell you if the difference between what you expected and what you got is risky. They can’t answer questions like:

- Did we build the right thing? 
- Has what we expected changed?
- How does it all fit together?
- If what we got has changed, is that a problem for the customer? 
- What didn’t we think of?

Valuable testing includes both automated and exploratory testing.

## How do you do exploratory testing?

Testers keep these things in mind as they’re exploring an application. (Skilled exploratory testers can describe their thinking to their team later, or even as they’re doing it.)

### 1. [A basis for comparison](https://developsense.com/blog/2012/07/few-hiccupps)

When you find something you don’t expect, you’ll need a way to explain to other people why you don’t expect it. In deciding whether something is unexpected, you might find yourself referring to:

- the history of the product
- the image of the product and organization
- claims made about the product by marketing, sales, documentation, conversations, user stories, etc. 
- user’s expectations
- other behavior within the product itself
- the product’s purpose
- statutes and standards (legal requirements, SLAs, accessibility standards)

### 2. [Rules of thumb and checklists](https://katrinatester.blogspot.com/2014/09/heuristics-and-oracles.html)

Having a list of ideas of things have gone wrong on software in general can help you identify similar patterns in your own product. They won’t prevent the unexpected, but having some ideas at your fingertips may help you uncover unexpected things earlier.

- [list of questions and a way to model the system](https://www.satisfice.com/download/heuristic-test-strategy-model)
- [thinking specifically about regression testing](http://karennicolejohnson.com/2009/11/a-heuristic-for-regression-testing/)

### 3. [Deciding what to focus on](https://www.kenst.com/exploratory-testing-charters/)

[Setting a mission for your exploratory testing helps you decide what’s in and out of scope, and what you’re trying to accomplish so you don’t get lost](https://pragprog.com/titles/ehxta/explore-it/). (Exploring is wandering with a purpose.) Try writing down:

1. where you’re exploring (the test environment, the new feature, etc.) 
2. what you’re using/how you’re exploring (the automated tests, the logs, the accessibility scanning browser extension, etc.)
3. what question you want to answer (are the existing tests passing, are we logging at the right level, has the extension uncovered new issues, etc.) 

Some examples of directions for your mission:

- [tours](https://www.michaeldkelly.com/blog/2005/9/20/touring-heuristic.html)
- [cheat sheet](https://www.ministryoftesting.com/articles/ab1cd85c?s_id=15905006)

## What’s hard about exploratory testing?

It’s not just poking around! It can be [hard to describe why, when, and how to do it](https://www.ministryoftesting.com/articles/0329e89e?s_id=15903802). Keeping all these things I’ve listed in mind [all at the same time takes practice](https://www.ministryoftesting.com/articles/1385fd4a?s_id=15903807). [It’s hard to know when you’re done](https://developsense.com/blog/2009/09/when-do-we-stop-test), or if you’ve done enough. And it’s usually [best to do both exploring and automating](https://web.archive.org/web/20230327105023/https://oldsite.workroom-productions.com/papers/ET%20Script%20or%20Explore.pdf), so finding time can be tricky or hard to advocate for. Having the brainpower to be [actively learning the whole time](https://medium.com/@maaretp/what-is-exploratory-testing-the-programmer-edition-881765411f2c) you’re doing your work is hard.

## All the links in one place

- [James Lyndsay's video about Wicked Problems](https://vimeo.com/275859034)
- [James Lyndsay's video about what's delivered vs. what's expected](https://vimeo.com/276040353)
- [Michael Bolton's blog post about "desirable consistencies between related things" summarized by FEW HICCUPS](https://developsense.com/blog/2012/07/few-hiccupps)
- [Katrina's Clokie's description of heuristics and oracles](https://katrinatester.blogspot.com/2014/09/heuristics-and-oracles.html)
- [James Bach's Heuristic Test Strategy Model](https://www.satisfice.com/download/heuristic-test-strategy-model)
- [Karen Johnson's heuristic for regression testing RCRCRC](karennicolejohnson.com/2009/11/a-heuristic-for-regression-testing/)
- [Chris Kenst's blog post on exploratory testing charters](https://www.kenst.com/exploratory-testing-charters/)
- [Elisabeth Hendrickson's book _Explore It! Reduce Risk and Increase Confidence with Exploratory Testing_](https://pragprog.com/titles/ehxta/explore-it/)
- [Michael Kelly's blog post on the touring heuristic](https://www.michaeldkelly.com/blog/2005/9/20/touring-heuristic.html)
- Updated version of the [Test Heuristics Cheat Sheet](https://www.ministryoftesting.com/articles/ab1cd85c?s_id=15905006) available from the Ministry of Testing
- [Simon Tomes's diagrams for describing exploratory testing](https://www.ministryoftesting.com/articles/0329e89e?s_id=15903802) available from the Ministry of Testing
- [Maaret Pyhäjärvi's article on self-management in exploratory testing](https://www.ministryoftesting.com/articles/1385fd4a?s_id=15903807) available from the Ministry of Testing
- [Michael Bolton's blog post about when to stop testing](https://developsense.com/blog/2009/09/when-do-we-stop-test)
- [James Lyndsay's article on why you've got to do both automation and human-powered testing](https://web.archive.org/web/20230327105023/https://oldsite.workroom-productions.com/papers/ET%20Script%20or%20Explore.pdf)
- [Maaret Pyhäjärvi's article on exploratory testing for programmers](https://medium.com/@maaretp/what-is-exploratory-testing-the-programmer-edition-881765411f2c)


