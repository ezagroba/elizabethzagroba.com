.. title: Finding relevant search results
.. date: 21 September 2020
.. tags: testing, search, risk-based-testing, exploratory-testing

In his crafting time, one of our developers decided to fine-tune our search results. He added relevancy scoring to give weights to different text fields. It was my job to determine if the right results were turning up at the top of the list of search results. So I had to ponder: what made a search result relevant? 

First, I realized that feedback from our users is the best way to answer this question. Anything I could do to get this feature out into production, where we'd get real data about what people searched for, would be more valuable that brainstorming test cases for this feature. I set myself a timebox of two and a half hours, the rest of the afternoon on a day in a week filled with competing priorities. We'd agreed as a team ahead of time that I could determine the testing approach, and our product owner would decide what was or wasn't worth fixing before this feature went out. 

I saved the first 45 minutes of my timebox to research what people had to say about search relevancy. Surely I was not the first person contemplating this problem. Over on the Ministry of Testing Club forum, I found what seemed to be a promising title of a post. [It turned out a past Elizabeth from a year ago wrote it, and nobody had answered it satisfactorily in the intervening time](https://club.ministryoftesting.com/t/how-would-you-test-a-search-api/28027). 🤦‍♀️

After Duck-Duck-Go-ing some actual answers, I found a couple of resources from websites I've trusted and found fruitful in the past: [A List Apart](https://alistapart.com/article/testing-search-for-relevancy-and-precision/) and [philosophe.com](https://www.philosophe.com/archived_content/search_topics/search_tests.html). A List Apart suggested honing in on a specific intent, searching for the queries users seek most frequently, and seeing how far those items fall from the top in the search results. The philosophe guidance about testing search gave me something deeper to consider: users shouldn't have to ponder the reasoning behind the search results. That was enough for me to develop some test cases. 

As I searched and adjusted the weights of various fields, plenty of normal things happened: setting the relevancy values to zero meant the result wasn't listed, multiple instances of the same word counted more than a single instance, and giving fields stronger weights caused their results to move up in the rankings. But as a bug magnet, I uncovered things that were both interesting to discover and outside the original scope of the story. 

![](/images/posts/2020/log-of-zero.png "Log of zero is negative infinity")

### Bugs 

1. I opted to edit data that was already in our test environment rather than setting up completely new data. In doing so, I discovered a couple description fields that were missing an indexing update in the search results when edited through the UI. 

2. I tried to use the default values for everything to see "normal" results. One field was going to add a value to the relevancy rating, so zero seemed like it should be the default option. Unfortunately a couple of the options for the weighting feature transformed the value using the `log` and `ln` (natural log) functions, which are undefined at zero. All my search results disappeared. 

3. I looked at the data that was already in the database, and used a search term that showed up a lot already. It turned up nothing. I searched for part of the word. That turned up all the results I was expecting. I realized the search term was indexed separately because of the characters we used to break the word apart. Imagine having a bunch of `sun-bleached` items, but you can only find them if you search for `sun` or `bleached`, not `sun-bleached`. 

Bug 1 the developer agreed was a bug, and we fixed as part of the story. Bug 2 was "working as expected" from a developer point-of-view, but seemed a little weird to the product owner. We meant to look into as part of the story and decide if we should eliminate the log functions as options entirely, but other priorities came crashing down upon before we could. It's out on production to the handful of internal users with access to the relevancy tuning. Bug 3 we added to the backlog, and I hope someday a swarm of user complaints make it a priority for us. 

### Morals

1. Users know best.
1. Someone else on the internet has had your problem before. 
1. Report information that matters.
1. When the risk is low, let it go. 
