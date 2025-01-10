.. title: Typing Faster Is Not The Problem.
.. date: 10 January 2025
.. description: Is A.I. coming for my job? Not this week. 
.. tags: automation, critical-thinking, humans, leadership, testing
.. previewimage: /images/posts/2025/colored-ines.jpg

We're in a tough spot these days. When a tester leaves the company, it can be hard to justify hiring another tester by looking at a balance sheet. The departure of even one tester, who supported a couple of teams, can impact the rest of the unit as quality declines and integration points deteriorate. 

A software development manager, faced with forces beyond their control, is in a tough spot. They're relying on fewer testers to do the work of maintaining a system that continues to change. In an effort to think about where we could speed things up, offload repetitive work, and free up our time for more interesting problems, a software development manager sent me and a few other testers this message today. [I abstracted some details.]


> Software Development Manager  [1:12 PM]

>... shoot me if I'm barging in on a topic that I'm not an expert in ... but :)

>Looking at the capacity we have in QA domain, optimising that is something I think about. Is the usage of [GenAI -> Github Copilot](https://www.frugaltesting.com/blog/automate-your-tests-with-github-copilot-a-step-by-step-guide) not an option. Takes away the scaffolding and grunt work and ... all the other valuable hype.

>We do have enterprise Github account with the corporate mothership.

It is a responsible manager move to ask the question "can this product we already have a license for make our work more effective?" I gave myself a chance to think it over. Here was my response:


> Me  [3:22 PM]

> I think if it the work i was doing was writing tests, an A.I. (as much as I hate the ecological consequences) might be an interesting choice. This week my testing work looked more like this:

> - reviewing the intern's kubernetes merge request and figuring out where functions could be abstracted, more specific assertions could be made, if we could delete a test.
- getting two applications for my new team running locally on my machine, and updating the README so the new developers on the team can do the same.
- understanding enough architecture diagrams from my new team to write bullet points on the testing story; then talking about it for a half-hour at the refinement meeting — long enough to realize the API endpoints I wanted to call don’t exist, and we should add a testability feature first.
- spending the rest of refinement discussing how we could prove the other task was completed, and that we need monitoring.
- looking at the failing k8s tests, figuring out a change happened on another team, confirming with Tester 1 the new UI behavior in their application and that only the first of the three test failures matters right now, removing some fixtures, and then getting stuck on a UI page that used to work because the selector Playwright automagically tells me to use actually returns two items instead of one unique one.

> If I come across work that a human is not necessary for, I would _gladly_ delegate it to a machine. I’m not sure which of these tasks I could hand over. (Let me know if other people have different kinds of work that can be delegated.)

> If where we’re stuck is on manual regression testing that a human has to do, would it be an option to pay a third-party service to do that testing just on the days before releases? [https://utest.com/](https://utest.com/) for example.

Two of the other three testers chimed in, one with support for my message, and both with more focus on the specific question the manager asked. They were interested to take an A.I. for a spin, and see what it could do. 

---

Did I miss the point of the question the software development manager was asking? Maybe. Maybe my colleagues' work, or my work on a different week, could benefit from a bit more auto-complete, a bit more "yes, that word was on the tip of my tongue, thanks IDE for putting it on my screen." 

But from where I sit, I don't think typing faster is the problem. [A wise man](https://smallsheds.garden/) has yelled "Typing faster is not the problem" enough times that I hear his voice in my head as I type it now. I am all for automation in testing. And I believe Github Copilot could not have improved my effectiveness this week. My work as a tester is highly technical, and it is fully of humanity. 

What do you see? How are you optimizing your work? Where is your work technical, and where is it in the technicalities? Do you do work that you could delegate to machine, and if so, have you? 
