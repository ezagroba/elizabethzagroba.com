.. title: This Diagram Asked More Questions Than It Answered
.. date: 16 January 2022
.. tags: testing, critical-thinking, dependencies

I made a diagram that asked more questions than it answered.

As Quality Lead for the seven engineering teams in my unit, I'm tasked with getting developers to think more holistically. I'm not an expert in any of the individual parts of the product teams are. I aim to have a bird's eye view on the whole, particularly when it comes to the testing we're doing. Each team is thinking about thorough coverage of their part; I'm looking at the through-line across the products.

So after only a few weeks on the job, when a particular behavior got the software development managers asking me "Did anyone test this end-to-end?" all I could say for sure was "I haven't!" It did get me thinking and asking them though:

- What do you mean when you say end-to-end?
- Did you mean an automated test, or someone trying it at least once manually? 
- Is the one path I have in mind the same one you're picturing?
- Is it important to have some type of coverage over every possible path, or can we decide to focus on the risky ones?

I started by drawing what I had in mind. It looked like this. The colored boxes show which team owns the code. The outlined boxes show actions a user could take. 

![](/images/posts/2022/step1.png "A humble beginning")

I went to it show people all around the department (developers, testers, product, UX, analytics, managers) so they could tell me where I was wrong or needed more detail. ([More on how that builds credibility in this post](https://elizabethzagroba.com/posts/2017/2017-08-06_doubt-builds-trust/)). 

Each person I showed it to added more boxes, or split existing boxes into more specific actions. Some even added more teams. I approached the teams humbly, acknowledging that though I was being asked about end-to-end testing, I didn't have a good view on what that meant right now. I acknowledged that they were the experts in the their own domains. I'd reviewed roadmaps and documentation to do what I could before I spoke to them so they only had to offer corrections instead of whole explanations. And I thanked them for correcting my ignorance and blind spots as we updated the diagram together. 

To our analytics expert, I said "I get asked a lot about the end-to-end flow, but I'm not sure what that means exactly. Do you have the same problem?" A wave of common struggle and understanding washed over them. 

By the time 15 people had given their perspective, the diagram had exploded into this monstrosity. 

![](/images/posts/2022/step2.png "A completely overwhelming mess")

This diagram was hard to read. It wasn't clear (to anyone but me) where the entry and exit points where. The key was hard to reference and had too much explanation. At a glance, the main takeaway was "This is complicated." This did live up to one of my goals: get people to see that "test everything end-to-end" is not a straightforward, single path. We wouldn't test every path or promise full coverage from the start (or ever, but that's [another conversation](https://elizabethzagroba.com/posts/2020/2020-05-24_if_a_test_falls_in_a_forest/)). But we could say: "There's a lot to cover here. Let's choose the most important path to start."

In showing the diagram to our sales and UX experts, and again acknowledging that this kind of diagramming was more their expertise than mine, I got nudged in the direction of business process modelling notation. I kept my teams and user actions in a way that notation didn't imagine, but putting everything in rows and columns gave my diagram an air of professionalism it didn't have before. 

![](/images/posts/2022/step3.png "Something bordering on approachable")


A different UX expert said they'd been too overwhelemed to try to process my overwhelming mess of a diagram, but they'd been able to read and learn from this attempt. 

Our software development managers and product experts were the ones asking about the state of end-to-end testing initially. Showing them the diagram got them thinking on the exactly the paths I wanted to trigger: 

- Can we have one of these for a different product we're building?
- What would this diagram look like if we only followed one user persona's journey?
- What else might be included in end-to-end if we think outside the scope of the seven engineering teams in our unit?
- How do people buy the product? How are they onboarded?
- How do people learning how to use the product discover these steps you've outlined? How do they know which direction they want to go?
- How do people make decisions at these decision points? How can we gain more insight into how they're doing that?

I think I probably could have helped perform some end-to-end testing with a collection of testers from the three teams I initially identifed in my first diagram, gone back to the managers and proclaimed "yes, we're end-to-end testing." But my job isn't to provide simple answers. It's to get people thinking about the whole, and asking the important questions for themselves. The journey of this diagram did exactly that. 

---

Do you find yourself answering questions that you see as misguided? How can you guide people to ask better questions? 