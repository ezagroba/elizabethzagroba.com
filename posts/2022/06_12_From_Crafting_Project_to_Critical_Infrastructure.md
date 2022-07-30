.. title: From Crafting Project to Critical Infrastructure
.. date: 18 June 2022
.. tags: python, apis, automation, code-review, testing
.. previewimage: /images/posts/2022/megaphone.jpg
.. description: State explicitly what you hope to achieve and how much effort you're willing to spend getting there.

## Just for me

Three years ago, I had a shit laptop. My company makes a Windows desktop software product that allows you to build your own applications. Mac users working the software could open it on their Windows virtual machine in Parallels. When I did that, my company's software crashed, Parallels crashed, and then my whole Mac crashed. My job was to create app builds, run them, and test them. Due to my shit laptop, I couldn't do that locally. 

Luckily, our app was also hosted in our public cloud. Through the cloud UI, you could make a build, see which build was on which of your environments, and deploying a new build. But the UI was...not an ideal workflow for me. It was slow to load, required several steps of clicking and waiting for a minute or two - just long enough to get distracted thinking about something else. A deploy process that might optimally take ~8 minutes took ~15 minutes as my mind wandered and the UI didn't update immediately. 

I needed a one-step process to deploy, with updates frequent enough to hold my attention. I decided to abandon the UI for the API. 

I wrote a Python script that took command-line input and printed output to the console as the steps of the process progressed. I used my two crafting days that month to break down the problem, setup the whole repository, and get the code to a state where it built and deployed an app to an environment. 

A code review from Joep Schuurkes moved the code from a long list of functions to different classes corresponding to the API endpoints I was calling. I think the commands were limited to `--build` and `--deploy`. To make sure the refactor was successful, I'd scroll up in my Terminal history and run those two commands again. Crafting days on subsequent months brought a bit more error-handling to account for mistypes on my side or failures/timeouts from the APIs. 

At this point, it was a solid tool that saved me about a half-hour per day. I presented it to the developers on my team, offering them access to the repository so they too could benefit from this time-savings. 

They were deeply unimpressed. They didn't have shit laptops, they had Windows laptops, they didn't have to run Parallels, they weren't constantly switching between branches and needing actual builds of the application to test. To them, this script was relatively useless. That was fine by me! The time and frustration the script saved me was more than worth the effort to build it. I used it several times a day myself, and got to use it as an example in the "Whole Team Approach to Continuous Delivery" workshop I paired with Lisa Crispin on. That was more than enough. 

![](/images/posts/2022/cloud-deployment-script.png "Slide from the workshop")

## Pipelines emerge

Six months later, a developer on my team got excited to set up a pipeline for our application. They wanted to run static code analysis on a build of our application, and run our functional tests against a deployed application running in a deployed environment. They copy + pasted my code as a starting point for the build and deploy, copy + pasted the static code analysis scans from another unit, and connected the two in a pipeline that provided value to the wider team. Developers weren't great at running tests on their feature branches on their machines; now we had a pipeline that would do it for them. 

Other teams saw our pipeline and discovered my deployment script in the process. Rather than copy + pasting the code as my teammate did, they pinned their pipelines to the most recent version of the code on the master branch. 

With more users and use cases, fellow colleagues were eager to also use their two crafting days per month to add the features they needed. I'd receive pull requests of things I didn't need for a context I didn't have, or feature requests I used my limited crafting time to fulfill. Without a style guide, a linter, tests, or a set scope, it was hard to turn away pull requests weeks or months in the making that people were eager to see included in the master branch. I merged it to keep everyone unblocked. As the code grew to serve every individual need, I lost  interest in supporting what had originally been my darling pet project. 

## Still Valuable? 

Two years after the original two-day crafting project, my role shifted from serving one team and one application to thinking about quality for the seven engineering teams in my unit. No longer did I need to deploy the application to a hosted environment. At the same time, my old team shifted where the repository was located, and the APIs I'd been calling in my script wouldn't do a lot of what they used to. 

I got to explore what it meant to be the Quality Lead for my unit, and nobody I served needed this script. I left the list of improvements I'd brainstormed for it languishing at the bottom of my personal Trello board. I didn't get any requests from other departments to use or update it. 

## Still Valuable!

Nine months later, the spark got reignited! A fork of the deployment script got presented in another unit, complete with a UI on top of it. Someone on my old project discovered my script, and decided to add a feature to upload builds from the new repository location to make it useful again. They shared the code for a review after just a few hours of effort. 

I had a chance to think through what parts of the repository were resuable for this use-case, which parts would be better copy + pasted for better readability, and got the merge request to a place where it fit in with the existing code style before anyone's heart and soul had been poured into it. 

Now a bloated script eight different actions, I decided to start writing tests for it. I didn't need the tests to make sure the existing code worked; everyone using it in their pipelines was enough to prove that. Tests will allow for future refactoring of the code and updating the version of the API I'm calling.

The first test I added confirmed that the new functionality did what the code submitter expected it to do, gave me a way to change individual parameters  faster. and gave me the confidence and excitement I'd been missing. 

I'm just getting going on tests for the rest of the existing code, but I'm looking forward to it!

--- 

Why do I tell you this story? Well, here's what I think when I look back at the evolution of this code base: 

- write tests, even before you *really* need them
- set up a linter and coding guidelines before you give anyone else access to your repo
- if you want to be precious about your code, tell people to fork instead of submitting merge requests
- if you want the code to be in its most findable place and shareable state, you'll have to invest the time to collaborate with people on their changes
- good things come to those who wait :)
