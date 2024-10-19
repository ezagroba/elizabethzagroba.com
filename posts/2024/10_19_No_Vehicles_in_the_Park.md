.. title: No Vehicles in the Park
.. date: 19 October 2024
.. description: When specification by example leads to an existential crisis
.. tags: communication, critical-thinking, exploratory-testing, note-taking
.. previewimage: /images/posts/2024/diversion.jpg

## Origin story

I found the website [No Vehicles in the Park](https://novehiclesinthepark.com/) through Mastodon. It asks you a series of questions describing a situation that you have to judge. For example: "Matthew pilots a commercial airliner over the park. Does this violate the rule?" It's a silly, fun time for dorks who like those kinds of things. 

![](/images/posts/2024/no-vehicles-site.png "What it looks like when you land on the website")

Testers are exactly those types of dorks. We love reading about Matthew flying a plane over the park and want to ask: what's the airspace of the park? How do we define a park? How do we define something being within or outside of the boundaries of a park? Has the plane's engine fallen out? 

If you've read [Exploring Requirements by Jerry Weinberg](https://leanpub.com/exploringrequirementsone), you're familiar with the "Mary had a little lamb heuristic", where each emphasis and variation opens up a new vector of possibilities: 

- _Mary_ had a little lamb - Who else had a little lamb? What else did Mary have?
- Mary _had_ a little lamb - Why doesn't Mary have the lamb anymore? Are Mary and the lamb ok?
- Mary had _a_ little lamb - Did Mary used to have more lambs? What happened to Mary's flock of lambs?
- Mary had a _little_ lamb - Does Mary also have a big lamb? Is this Mary's small lamb or is the lamb underweight?
- Mary had a little _lamb_ - Does Mary have snakes?

I knew No Vehicles in the Park had the same kind of energy, and it would be fun to bring it to a group.

## Online at Friends of Good Software

The knowledgeable goofballs at the [Friends of Good Software Conference](https://frogsconf.nl/) were subjected to this thought experiment in March of 2024. Here are the notes from that 45-minute session.

![](/images/posts/2024/no-vehicles-at-frogs.png "Notes from the Friends of Good Software session, where many great ideas are born and nurtured")

I shared my screen and pulled up a mindmap on the Miro board where we decide our sessions and take notes during the open space. When I asked "what is a vehicle?" the group started listing examples rather than providing a definition. Pasting the results from image searches made sure we each understood the thing being described. 

Once we felt we had "enough" (spoilers: it was not enough), we moved on to the 27 questions. I kept the website with the question in one browser tab on one side of my screen, the Miro board with the notes in a different browser tab on the other side of my screen, and the video with the participants on my other monitor. 

For each question, I read it out loud and asked "does this violate the rule?" Participants held their thumb up for "it violates the rule", thumb down for "it does not violate the rule", and sideways for still deciding, conflicted, or annoyed by the question. Usually the vote was enough to spur someone to verbally defend their position. I watched the body language of the participants to assess if people had been swayed. After a minute or two of discussion, I double-checked the vote, declared my intention about which button I would press out loud to confirm I'd counted thumbs correctly, and pressed it. 

The session and the debrief provided us an opportunity to reflect on the rule "No vehicles in the park" and our reaction to it. Some of our notes include questions like: is violating the rule allowed? do you want it to happen regardless of the rule? what's the desired behavior vs. prohibiting undesired behavior? We had a discussion about the cultural (and individual personality) differences when you prohibit something vs. allow something. 

This may have been the hardest I've laughed during a Friends of Good Software session, which I've been co-organizing for five years. That someone proclaimed "Shoes are not the master of us!" within the first few minutes gives you some idea of how silly and off-the-rails this session felt overall.

## In-person at Hungarian Software Testing Forum

Last week I ran the session again in-person at the [Hungarian Software Testing Forum (HUSTEF)](https://hustef.hu/). As part of the program committee, I was tasked with identifying "fun" activities for the group. I regret to inform you this is my idea of fun. 

I wasn't sure what the tech or chair setup would be in the room before I arrived, so I envisioned me reading out the questions with people running from side-to-side depending on whether they agreed or disagreed with the question. We ended up in the largest room with hundreds of chairs attached to the floor, so that wasn't going to work. Plus we were doing it at 6pm. People had fizzy drinks in their hands and were ready to sit and enjoy them. 

We agreed to stay seated and use our thumbs. I figured out how to connect my laptop to the screen on stage so everyone could read the site. I started by asking for definitions of “vehicle” and “park”, and wrote those down, until it felt like enough. Of course it wasn’t enough! 

I read each question out loud and immediately got a thumb vote: thumbs up for this is a vehicle, thumbs down for this is not a vehicle, sideways thumb for any other feelings. (Phrasing it as "is a vehicle" and "is not a vehicle" proved much clearer for participants.) I’d call on someone at random, or who put their thumb up soonest, to ask them to explain their choice. I toggled back and forth between the definitions and the 

I kept things moving quite a bit. (My style got compared to that of an auctioneer.) After an explanation or two, I’d take a revote if people seemed to have changed their minds, or announce which button I was going to click to give people the chance to veto. 

We briefly debriefed with a conversation about requirements, but mostly people were happy to get back to the other more social events for the evening. The thing that people wanted as we went along was a continuum, of "most vehicle-y" to "least vehicle-y" where we'd put each item. We kept asking "wait, what did we say about the last thing like this?" Here are [the notes](/images/posts/2024/no-vehicles-at-HUSTEF.jpg) and a couple photographs captured of the group. 

![](/images/posts/2024/concern.jpg "A collection of testers truly struggling to synthesize their past decisions into the current one")


![](/images/posts/2024/thumb-vote.jpg "Thumb vote: up for it is a vehicle, down for it is not a vehicle, some still conflicted")

## What's the point?

I don't think there has to be a point to something silly and fun. Silly and fun can be enough. 

But if you're interested in there being a point, here are some options: 

1. Tie-in to specifying requirements: This is originally what I had in mind when I saw it, but ultimately the silliness and "my brain feels broken" aspects were larger for both groups relatively late in the day. 
2. Practice writing a user story: Start with the definition of "vehicle", "park", "in", as many as you think you need. As you go through the questions, do not list any examples, but do edit and add to your definitions so they capture each new use case. 
3. Practice facilitating a refinement meeting: As a frequent facilitator of refinement meetings, I've cultivated the skill of getting people to vote on a thing (typically story points), discuss it "enough" for now, and move on. I'd recommend running this session to anyone needing a bit more practice in [cutting people off](https://elizabethzagroba.com/posts/2021/cutting_people_off/), bringing people back to focus, or typing while screen sharing.
4. Practice or compare-and-contrast note-taking styles: Something I'd like to try for a future session is to use this as note-taking practice. Seed different invididuals with ideas about how to take notes: pro/con style two-sided list, timeline or continuum, bullet points, mindmap, etc. Don't take any notes yourself as the facilitator, or let people focus on which button you're clicking. Share your screen only to keep everyone on the same questions at the same time. For the debrief, have all the people seeded with the same note-taking idea compare notes first, then split up the groups so everyone's debriefing with a note-taker in a different style. 
5. The original intent of the website designer: When you get to the end of the 27 questions, there are a few paragraphs describing why this website was built in the first place. I won't spoil it for you, but it might be an interesting way to spark a certain type of discussion with a group of people who might not normally self-select into such a topic. 

---

### Thank you

Thanks for all the people at FroGSConf and HUSTEF for joining the No Vehicles in the Park sessions. Special thanks to the HUSTEF organizers, who promoted this social event without fully understanding what was going to happen!

Let me know if you've run a session with a group, what the outcome was, and what nonsense scenario is playing out as a thought experiment now that you've done this.

<blockquote class="mastodon-embed" data-embed-url="https://chaos.social/@ez/113278801908610903/embed" style="background: #FCF8FF; border-radius: 8px; border: 1px solid #C9C4DA; margin: 0; max-width: 540px; min-width: 270px; overflow: hidden; padding: 0;"> <a href="https://chaos.social/@ez/113278801908610903" target="_blank" style="align-items: center; color: #1C1A25; display: flex; flex-direction: column; font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Oxygen, Ubuntu, Cantarell, 'Fira Sans', 'Droid Sans', 'Helvetica Neue', Roboto, sans-serif; font-size: 14px; justify-content: center; letter-spacing: 0.25px; line-height: 20px; padding: 24px; text-decoration: none;"> <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="32" height="32" viewBox="0 0 79 75"><path d="M74.7135 16.6043C73.6199 8.54587 66.5351 2.19527 58.1366 0.964691C56.7196 0.756754 51.351 0 38.9148 0H38.822C26.3824 0 23.7135 0.756754 22.2966 0.964691C14.1319 2.16118 6.67571 7.86752 4.86669 16.0214C3.99657 20.0369 3.90371 24.4888 4.06535 28.5726C4.29578 34.4289 4.34049 40.275 4.877 46.1075C5.24791 49.9817 5.89495 53.8251 6.81328 57.6088C8.53288 64.5968 15.4938 70.4122 22.3138 72.7848C29.6155 75.259 37.468 75.6697 44.9919 73.971C45.8196 73.7801 46.6381 73.5586 47.4475 73.3063C49.2737 72.7302 51.4164 72.086 52.9915 70.9542C53.0131 70.9384 53.0308 70.9178 53.0433 70.8942C53.0558 70.8706 53.0628 70.8445 53.0637 70.8179V65.1661C53.0634 65.1412 53.0574 65.1167 53.0462 65.0944C53.035 65.0721 53.0189 65.0525 52.9992 65.0371C52.9794 65.0218 52.9564 65.011 52.9318 65.0056C52.9073 65.0002 52.8819 65.0003 52.8574 65.0059C48.0369 66.1472 43.0971 66.7193 38.141 66.7103C29.6118 66.7103 27.3178 62.6981 26.6609 61.0278C26.1329 59.5842 25.7976 58.0784 25.6636 56.5486C25.6622 56.5229 25.667 56.4973 25.6775 56.4738C25.688 56.4502 25.7039 56.4295 25.724 56.4132C25.7441 56.397 25.7678 56.3856 25.7931 56.3801C25.8185 56.3746 25.8448 56.3751 25.8699 56.3816C30.6101 57.5151 35.4693 58.0873 40.3455 58.086C41.5183 58.086 42.6876 58.086 43.8604 58.0553C48.7647 57.919 53.9339 57.6701 58.7591 56.7361C58.8794 56.7123 58.9998 56.6918 59.103 56.6611C66.7139 55.2124 73.9569 50.665 74.6929 39.1501C74.7204 38.6967 74.7892 34.4016 74.7892 33.9312C74.7926 32.3325 75.3085 22.5901 74.7135 16.6043ZM62.9996 45.3371H54.9966V25.9069C54.9966 21.8163 53.277 19.7302 49.7793 19.7302C45.9343 19.7302 44.0083 22.1981 44.0083 27.0727V37.7082H36.0534V27.0727C36.0534 22.1981 34.124 19.7302 30.279 19.7302C26.8019 19.7302 25.0651 21.8163 25.0617 25.9069V45.3371H17.0656V25.3172C17.0656 21.2266 18.1191 17.9769 20.2262 15.568C22.3998 13.1648 25.2509 11.9308 28.7898 11.9308C32.8859 11.9308 35.9812 13.492 38.0447 16.6111L40.036 19.9245L42.0308 16.6111C44.0943 13.492 47.1896 11.9308 51.2788 11.9308C54.8143 11.9308 57.6654 13.1648 59.8459 15.568C61.9529 17.9746 63.0065 21.2243 63.0065 25.3172L62.9996 45.3371Z" fill="currentColor"/></svg> <div style="color: #787588; margin-top: 16px;">Post by @ez@chaos.social</div> <div style="font-weight: 500;">View on Mastodon</div> </a> </blockquote> <script data-allowed-prefixes="https://chaos.social/" async src="https://chaos.social/embed.js"></script>


<br/>