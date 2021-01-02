.. title: The Flow of Two Exploratory Testing Sessions
.. date: 26 December 2020
.. tags: exploratory-testing, testing, teaching
.. previewimage: /images/posts/2020/work-ensemble.png

The [Exploratory Testing Peer Conference](https://exploratorytesting.org/) [#ET19](https://twitter.com/search?q=%23et19&src=typed_query) followed the 2019 Valencia edition of the European Testing Conference. I said something that I pretty immediately forgot in the upheaval when I returned to the office, but it really stuck with [Anne-Marie Charrett](https://twitter.com/charrett). I appreciate both that she remembered this at all, and continues to insist that I'm the one who had this stroke of genius when she really brought it to life. Here's the idea: 

It's straightforward to follow one thread or idea through an exploratory testing session. It's not straightforward to decide which path to take, feed information from one path back into another, recognize that there are different paths, or bring others along for this journey. 

### The Ensemble at Work

We have a weekly ensemble testing session at my workplace. For an hour and a half, testers from different teams working in the same tech stack come together to share knowledge and build testing skills. In a recent ensemble testing session, a tester on one team brought a ticket they'd been avoiding tackling on their own. They knew they didn't know how to test the fix. But they felt like they'd talked about it enough as a team that they should have understood what to do already. 

We read through the story with the group of testers. We determined that a static code analysis security scan had discovered vulnerabilities in a couple of libraries. The developers had fixed the issue by removing the libraries. It was our mission to make sure those libraries were removed. 

Immediately a plan came to my mind:
1. Map out what kinds of pages there were, assuming that different pages of the same type would be likely to load the same libraries: list view, detail view, landing page, etc. 
1. Look at one of each of those pages with the Network tab open in the developer tools.

In a quick spirt of excitement, I dumped this idea on the group without figuring out if people knew what either of these things meant. (It turns out, not everyone did.) But everyone seemed to understand that there was somewhere in the developer tools where we could tell which libraries were loaded, so we started there. Exploring in a group is not about getting everyone to follow my idea immediately (or ever), it's about making sure everyone is on board and understands what's going on.

Proving the absence of a thing is harder than proving the presence of something, so we spent a bit of time looking through the Console and Storage tabs, as well as reloading the page with the Network tab opened, to figure out what appeared where. That helped everyone remember or discover that we didn't need to reload the page if the Network tab was open before the page loaded. This sped us up for the rest of the session.

Next, we looked at a couple of similar-looking list pages. We searched for the libraries in the Network tab. They weren't there. Now that we'd seen a couple of examples, I decided it was the right time to bring up my original idea of grouping pages by type. (Going from the abstract to the concrete doesn't work for everybody, so sometimes going from the concrete to the abstract works better.) I asked "These last two pages both looked like list pages, what other kinds of pages are there? Can we list them? Should we look at a detail page?" This comment blew the mind of the tester who brought this ticket. They'd been testing this product for two years and had never organized the product this way in their brain. It may not have occurred to them that a product *could* be organized in different ways in their thoughts depending on the circumstance. We got as part as listing the concrete pages we'd checked, but not as far as identifying all the types in the abstract before the energy in the ensemble moved on.

We looked at a detail page. We looked at a settings page. Then one of the testers who's been looking at a lot of front-end Javascript noticed two things: both the URLs we were searching for had `ajax` in them, so we only needed to search for one thing on each page we opened. And second, they knew that ajax was used to make changes to pages that had already loaded, so they asked "what kinds of pages change after they're loaded?" In this particular application, it was mostly forms in pop-up windows, so we concentrated our efforts there for the rest of the session. 

The whole session took about an hour and a half. A tester that came in scared and confused left empowered, with information to bring to their developers, and  a plan for how to execute the rest of the testing. Here's one way of looking at our exploratory testing session:

<a href="/images/posts/2020/work-ensemble.png"><img src="/images/posts/2020/work-ensemble.png" /></a>

At every stage, we absorbed a lesson as a group, and used it as our new superpower to make our testing better for the next bit. There were other paths we could have pursued, but many of these weren't consciously mentioned or acknowledged during the session.


### The Ensemble at the Conference

I facilitated a couple of ensemble sessions with groups at Agile Testing Days. Our first emsemble had a couple people drop out, so it ended up being one tester, one developer, and me. We were looking at a [very straightforward application](https://eviltester.github.io/TestingApp/apps/7charval/simple7charvalidation.htm) from Alan Richardson where you can decide whether a string contains 7 characters and is valid (in the set A-Z, a-z, 0-9, and * ). A few different times the developer and I asked if we should look at the source code. Rather than trying to interrogate the application based on the behavior from different inputs (black box testing), we wanted to go to the source (white box testing). 

But we never did. We kept trying different inputs, getting increasingly creative with order, special characters, Unicode characters, other languages as we progressed. But we never chose a different path. Even as I tried to encourage us to take notes so we wouldn't try the same things we'd already tried, we didn't. 

<a href="/images/posts/2020/atd-ensemble.png"><img src="/images/posts/2020/atd-ensemble.png" /></a>

We did manage to find a good resource for copying and pasting unicode characters, but we didn't learn how to explore the application more efficiently, or take what we learned earlier in the session to apply it to the rest of the session.


### The Power of Exploratory Testing

Brute force will get you somewhere. Trying enough different inputs, or different pages, and you'll gather more information about how the application works. But the power of exploratory testing comes from learning from your earlier results. It's realizing there are different ways to go, different paths to follow, jumping on one of those while it serves you, and making sure everyone else is along for the ride. 