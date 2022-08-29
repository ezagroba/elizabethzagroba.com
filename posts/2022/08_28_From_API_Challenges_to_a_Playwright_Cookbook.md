.. title: From API Challenges to a Playwright Cookbook
.. date: 28 August 2022
.. description: Writing Python in an ensemble with Maaret Pyhäjärvi and Alex Schladebeck.
.. tags: automation, playwright, testing, python
.. previewimage: /images/posts/2022/playwright.png


Soon after [Maaret Pyhäjärvi](https://twitter.com/maaretp) and [Alex Schladebeck](https://twitter.com/alex_schl) began their endeavor to practice testing APIs using the [API Challenges](https://www.eviltester.com/page/tools/apichallenges/) from [Alan Richardson (aka The Evil Tester)](https://twitter.com/eviltester), they looped me into their periodic practice sessions. Why? To make Past Elizabeth jealous, presumably. 

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Continuing on the api challenges from <a href="https://twitter.com/eviltester?ref_src=twsrc%5Etfw">@eviltester</a> with <a href="https://twitter.com/alex_schl?ref_src=twsrc%5Etfw">@alex_schl</a> and <a href="https://twitter.com/ezagroba?ref_src=twsrc%5Etfw">@ezagroba</a> after weeks of being otherwise engaged, always happy to have see where we left off with a test. Simple thing for our future selves in group learning activity. <a href="https://t.co/D99nC2PDVX">pic.twitter.com/D99nC2PDVX</a></p>&mdash; Maaret Pyhäjärvi (@maaretp) <a href="https://twitter.com/maaretp/status/1468883485205147652?ref_src=twsrc%5Etfw">December 9, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>



# API Testing Challenges

We gathered for an hour every few weeks to work through the challenges. The tools we were using ([pytest](https://docs.pytest.org/en/7.1.x/), the [Python requests library](https://pypi.org/project/requests/), and [PyCharm](https://www.jetbrains.com/pycharm/)) were like home for Maaret and me. I'd been writing in a framework with these tools for my job for a few years already. 

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Today in API testing adventures with <a href="https://twitter.com/maaretp?ref_src=twsrc%5Etfw">@maaretp</a> : We&#39;re profiting greatly from <a href="https://twitter.com/ezagroba?ref_src=twsrc%5Etfw">@ezagroba</a> &#39;s python syntax expertise, and we&#39;re learning to doubt our oracles ;)</p>&mdash; Alex Schladebeck (she/her) (@alex_schl) <a href="https://twitter.com/alex_schl/status/1447894251384233984?ref_src=twsrc%5Etfw">October 12, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

I wasn't the only one. These tools were free to use and available for a number of years already. What the three of us combined couldn't figure out by trial-and-error, reading the error message, reading the darn description of what we were supposed to do again, or relying on patterns from previous exercises, we were able to Google. With one notable exception of course, as we are testers after all: 

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Today&#39;s API testing challenges with <a href="https://twitter.com/ezagroba?ref_src=twsrc%5Etfw">@ezagroba</a> and <a href="https://twitter.com/maaretp?ref_src=twsrc%5Etfw">@maaretp</a> : the python requests library does not support TRACE...</p>&mdash; Alex Schladebeck (she/her) (@alex_schl) <a href="https://twitter.com/alex_schl/status/1468892681715822593?ref_src=twsrc%5Etfw">December 9, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

It may not *seem* like you'd need three people to do the work that one person could do. But I assure you, having extra pairs of eyes to catch a typo, remember whether we were expecting it to pass or fail this time, see immediately that it's a whitespace issue making PyCharm angry, crack a joke, or help decide whether to keep going in the same direction makes the work go more smoothly. 

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Observation from today&#39;s API testing session with <a href="https://twitter.com/ezagroba?ref_src=twsrc%5Etfw">@ezagroba</a> and <a href="https://twitter.com/maaretp?ref_src=twsrc%5Etfw">@maaretp</a> - it takes multiple people to remember all the details. A very succint way of summarising why we need to collaborate </p>&mdash; Alex Schladebeck (she/her) (@alex_schl) <a href="https://twitter.com/alex_schl/status/1478297685039976449?ref_src=twsrc%5Etfw">January 4, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

More than once, we'd end a session a few minutes early because we were stuck and lost, only to come back a couple weeks later with fresh eyes, able to understand where we were stuck and what to do about it. After several months meeting infrequently, we got through all of the API Testing Challenges! 

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">We survived! Success! All of the <a href="https://twitter.com/eviltester?ref_src=twsrc%5Etfw">@eviltester</a>&#39;s API Test Challenges complete! I love working with this team <a href="https://twitter.com/ezagroba?ref_src=twsrc%5Etfw">@ezagroba</a> <a href="https://twitter.com/maaretp?ref_src=twsrc%5Etfw">@maaretp</a> <a href="https://t.co/xGKQOkW3gb">pic.twitter.com/xGKQOkW3gb</a></p>&mdash; Alex Schladebeck (she/her) (@alex_schl) <a href="https://twitter.com/alex_schl/status/1488520727649206288?ref_src=twsrc%5Etfw">February 1, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Then we were like...now what? We like learning together, but we'd achieved our goal. 

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Now we&#39;re talking about our next learning goals: mine are &#39;learning anything with awesome people&#39; <a href="https://twitter.com/maaretp?ref_src=twsrc%5Etfw">@maaretp</a> <a href="https://twitter.com/ezagroba?ref_src=twsrc%5Etfw">@ezagroba</a></p>&mdash; Alex Schladebeck (she/her) (@alex_schl) <a href="https://twitter.com/alex_schl/status/1488521161923252224?ref_src=twsrc%5Etfw">February 1, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>



# Starting out with Playwright

After a bit of brainstorming, we landed on a skill Alex and I were both still building: UI automation. Naturally, Maaret was way ahead of us, and pointed us towards Playwright framework and [a practice site](http://selenium.thinkcode.se/) from [Thomas Sundberg](https://twitter.com/thomassundberg) of all the greatest hits: radio buttons, drop-downs, alerts, you name it. 

Our experience with UIs, DOMs, automation, Selenium, exploration helped us, but didn't prevent every pickle we got ourselves into with Playwright. Though [their documentation](https://playwright.dev/python/docs/intro) will tell you a lot of what you need to know (if you've correctly selected Python instead of Java or Node.js at the top), our desperation kept exceeding our patience. We escalated to the Playwright champion [Andrew Knight](https://twitter.com/AutomationPanda/) and the Playwright community Slack channel.  

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">I&#39;m not sure about that. Can anyone from <a href="https://twitter.com/playwrightweb?ref_src=twsrc%5Etfw">@playwrightweb</a> help answer?</p>&mdash; Pandy Knight (@AutomationPanda) <a href="https://twitter.com/AutomationPanda/status/1511346210434654219?ref_src=twsrc%5Etfw">April 5, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Several times, it wasn't only the code that needed changing, but our perception of how Playwright wanted to interact with the website. These are a few I remember: 

1. an API response from a browser context can't be collected from a page context
2. setting different contexts for a page and an alert on that page
3. having that alert knowledge not help us when we also had to fill in a prompt
4. expecting something in the DOM to tell us when an item in drop-down was checked

<blockquote class="twitter-tweet"><p lang="en" dir="ltr"><a href="https://twitter.com/maaretp?ref_src=twsrc%5Etfw">@maaretp</a> <a href="https://twitter.com/alex_schl?ref_src=twsrc%5Etfw">@alex_schl</a> A kind gentleman in the Playwright Slack pointed us here: <a href="https://t.co/e12v4nhth5">https://t.co/e12v4nhth5</a><br><br>It returns the value `milk` but not the visible text `Milk` of what&#39;s selected. Perhaps that&#39;s good enough!</p>&mdash; Elizabeth Zagroba (@ezagroba) <a href="https://twitter.com/ezagroba/status/1528999806928048130?ref_src=twsrc%5Etfw">May 24, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

For the first three, wrapping our heads around a different way of thinking got us through the problem. For the last on, we lowered our expectations about what we could check. (Pun intended.) 

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Learning more on <a href="https://twitter.com/hashtag/playwright?src=hash&amp;ref_src=twsrc%5Etfw">#playwright</a> with <a href="https://twitter.com/ezagroba?ref_src=twsrc%5Etfw">@ezagroba</a> and <a href="https://twitter.com/alex_schl?ref_src=twsrc%5Etfw">@alex_schl</a> and coming to realisation we are modelling the world wrong and thus having harder time discovering info on the API documentation. We need to remodel our worlds.</p>&mdash; Maaret Pyhäjärvi (@maaretp) <a href="https://twitter.com/maaretp/status/1537423632632266752?ref_src=twsrc%5Etfw">June 16, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>



# Playwright Cookbook

We've tested what we can and should test on our first practice site. In upgrading to a more challenging one, we realized that we'd benefit from the knowledge our past selves gained. And that you could too. 

We've published our progress on github as the [Playwright Cookbook](https://github.com/ezagroba/playwright-cookbook
). It's a Python repository of what we found that worked for different UI situations. It's one step beyond the Python documentation on the Playwright website, it lets you compare an actual page to a test where we were able to select the element. 



# Fun was had by all

Trying to quickly get something done with a new UI automation tool had been my white whale, something I knew was annoying enough that I wouldn't know how to get unstuck. Working in an ensemble meant either (1) the knowledge we needed was in the room and just had to be shared, or (2) two brilliant, successful ladies known for their testing prowess also didn't have a clue what was happening. Either way, it made things better and achievable. 

I am notoriously opposed to fun. But this has been fun. 

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">&quot;You only get to do fun exploratory testing after you have first automated it. That is the rule.&quot; Making fun of us exploring continuously when playing with <a href="https://twitter.com/hashtag/Playwright?src=hash&amp;ref_src=twsrc%5Etfw">#Playwright</a> with <a href="https://twitter.com/alex_schl?ref_src=twsrc%5Etfw">@alex_schl</a> <a href="https://twitter.com/ezagroba?ref_src=twsrc%5Etfw">@ezagroba</a></p>&mdash; Maaret Pyhäjärvi (@maaretp) <a href="https://twitter.com/maaretp/status/1542443256977424391?ref_src=twsrc%5Etfw">June 30, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">The added fun and energy in learning hands-on things together creates an environment where we want to show up and learn. Social software testing for learning, FTW!</p>&mdash; Maaret Pyhäjärvi (@maaretp) <a href="https://twitter.com/maaretp/status/1542451911676272640?ref_src=twsrc%5Etfw">June 30, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 



# What's next

What is next for us? We know we want to:

- keep learning together
- add more recipes for [our next testing target](https://the-internet.herokuapp.com/)

Have we reflected on what's valuable and not valuable to test on an API? Will we share more about this beyond this blog post? A conference talk or workshop? A Twitch stream?? Only time will tell. For now, enjoy the github repo. :)

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Perhaps instead of proposing to show up in conferences to do our learning sessions, we should start a twitch stream on our learning sessions <a href="https://twitter.com/alex_schl?ref_src=twsrc%5Etfw">@alex_schl</a> <a href="https://twitter.com/ezagroba?ref_src=twsrc%5Etfw">@ezagroba</a> :D</p>&mdash; Maaret Pyhäjärvi (@maaretp) <a href="https://twitter.com/maaretp/status/1542471658220527617?ref_src=twsrc%5Etfw">June 30, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
