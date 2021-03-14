.. title: When You Can't Help Much, Help A Little
.. date: 14 February 2021
.. tags: testing, reporting


### Check that you have time

At my current job, everyone in the R&D department gets a budget of two days per month to spend "crafting," or researching, building, testing, etc. what interests them. Most often people use this time to bring work they're passionate about up from the bottom of the backlog to be worked on now.

I was in the middle of adding a security scanning tool to our CI pipeline when I happened upon something interesting to test: a new web application. An old application that had been widely-used around the company, and as it turns out, with our customers too, had gone down. It allowed you to share a piece of text with a link. The text was only visible once. It wouldn't be viewable subsequent times you followed the link, so the application was good for sending passwords around securely. 

The person who'd built the application had left the company. In inquiring about who/how we might maintain it now, one of the customer support leads mentioned in a public Slack channel that he'd built a replacement. "Great!" I thought. "This is the one day I have an hour to test it." I was waiting for code review feedback on my pipeline scan, so it was perfect timing.

### Check that the feedback will be heard

It's a waste of time and energy (with the latter being in shorter supply these days) to test something if nobody's going to do anything with the results of your testing. More on that in [this post](https://elizabethzagroba.com/posts/2020/2020-05-24_if_a_test_falls_in_a_forest/). So I checked with the customer support person first. After taking a quick look at the new application and confirming that it seemed to work, but could use some tweaks, I asked the customer support person in a direct message if he was ready for usability and accessibility feedback. 

> Me: Hi there, I have a bit of usability and accessibility feedback about the secrets app. Is it at a stage where this feedback would be useful?

> Him: Yes, definitely 🙂

> Me: Great, I'll send you a Paper doc this afternoon.

### Collect the feedback in the same way it will be presented, and present feedback in a way that the audience is comfortable with

As much as I love making mindmaps, I decided that might not be the best format in this case. I doubted the customer support lead would bother to download a mind mapping application, company security restrictions prevented me from sharing a web-based one, and I'd probably want to walk him through a mind map I produced. But that felt like too much trouble for something small, plus I didn't want another Zoom call on a day otherwise free from them. 

Instead, I used my company's go-to document tool of choice: Dropbox Paper. I might not enjoy it as much, but I knew it was a way he was used to receiving and collaborating asynchronously. I confirmed that format with him to be sure, and then I got to testing. 

### Share your oracles (reasons why you have feedback)

Once I opened a one-time link the application created, there was a page with an animated GIF, the piece of text that was shared, and a button to `Copy Value`. My immediate testing notes were something like:

- Remove GIF/make it stop rotating
- Move button to the top
- Make font bigger

This customer support lead might have just taken than feedback and made the changes. But since I don't have an existing relationship where I provide feedback about his work, and developing applications is not his normal line of work, I provided more details: 

- Animated GIFs (that can't be turned off) can trigger people with epilepsy or motion disorders (vertigo for example). [Here's the W3C guideline on this](https://www.w3.org/WAI/tips/designing/#provide-controls-for-content-that-starts-automatically). 
- Move the `Copy Value` button above the text you're sharing so it's visible even if the text is ~5000 characters long.
- Increase the font size from the current 14px to 16px for vision-impaired peoeple. The ADA and typography geeks recommend 16, Apple has 17 as their font size. 

Now the customer support lead  understands why I'm asking for these changes. He can make different decisions than exactly what I've suggested while still addressing the problem I'm reporting. Plus he'll know more for next time he's building something. 

### Acknowledge the limits of the situation

Somewhat to my surprise, the customer support lead  started implementing my feedback right away! He took what I said into account, including removing the animated GIF entirely. He appreciated my feedback and wanted me to look at the application again the next day. Unfortunately, the next day was back to a regular work day filled with priorities, pressure, meetings, etc. I told him I wasn't going to have time to test it again. He went ahead and launched a functioning product. 

### Move on

While testing the product, another colleague noticed that the application had a larger architecture and setup than strictly what was needed for this particular use-case. Also, the application didn't provide an API for applications instead of humans to be sending around secret links to other humans. I defended the customer support lead: he was doing his best to solve his problem with the tools and skills he had. It wasn't the right time or place to come in at the end of a project that was about to provide value to people (myself included) and announce "this was not the optimal way to build this tool." You don't have to share all the feedback you collect. 

## Summary
The next time you're wondering if you should parachute in to test something new, consider these steps: 

- check that you have time
- check that the feedback will be heard
- collect the feedback in the same way it will be presented
- present feedback in a way that the audience is comfortable with
- share your oracles (reasons why you have feedback)
- acknowledge the limits of the situation
- move on
