.. title: Story Slicing Workshops
.. date: 31 October 2022
.. tags: workshop, development, handoff, mindset
.. previewimage: /images/posts/2022/elephant.JPG
.. description: Getting a team to break their user stories into smaller pieces. 

I remotely facilitated [this story slicing workshop](https://docs.google.com/document/d/1TCuuu-8Mm14oxsOnlk8DqfZAA1cvtYu9WGv67Yj_sSk/pub) created by Henrik Kniberg and Alistair Cockburn for two of the teams in my unit recently. They named it "Elephant Carpaccio" to give people the mental image of breaking down a big feature into very thin, vertical slices. Joep Schuurkes brought it to my attention when he facilitated the workshop a couple times in 2021, leaving behind not only [these very helpful blog posts about how to run it](https://smallsheds.garden/categories/elephant-carpaccio/) but also the Miro board he used to do so. 

![](/images/posts/2022/elephant.JPG "My elephant encounter")

## The Setup

The 2.5 hour workshop as Joep ran it included three conversations: 

- a conversation about why we might split stories
- a description of today's feature we'll be building
- a short brainstorm about what would be a good (small enough) first slice of this feature

These three parts would fill the first 45 minutes. The rest of the workshop would be smaller groups tackling each of these tasks in bigger chunks of time:

- breaking down the problem into between 10 and 20 stories
- actually building the first few stories as sliced
- a reflection and debrief on the whole workshop

## The First Group

In my first running of the workshop, I was able to see a few things I didn't expect in the story breakdown: 

1. American state abbreviations: The problem lists different values of sales tax for AL, TX, and three other abbreviations Americans would typically know. Participants wanted to talk about the states using their names, but didn't know which abbreviation belonged to which state. I filled them in on the table I created. 
2. Sales tax vs. VAT: Another American vs. European participant thing! The answer to "how much does the thing cost?" will be different if you're adding the tax to the price, or assuming it will be included in the total. This wasn't important to the solving of the problem, so I let this difference persist. 
3. First things first: the calculating of the price was laid out very clearly as the first problem to solve. One persistent participant really had their heart set on data input validations and a particular user interface. It took several tries from their teammates and ultimately my nudging to encourage them to think about the problem from the most important pieces first. 

I switched the instruction to take a demo/screenshot every 8 minutes, and instead asked groups to make one after each slice. This helped raise awareness for the difference between how they were breaking down the work, and how they were actually picking up the work. They might get through two or three slices in one go, only to have to go back and demo each scenario individually. 

A few insights came through more clearly in the debrief than during the exercise:

- It was easier to see progress and celebrate it when the work was broken down into smaller pieces. 
- The team understood the concept a lot better now, but there was still a big delta between how small they _could_ slice a story, and what would make sense when the burden of code review and testing would typically take a few days. 
- A thinly sliced story is not the same as an MVP.

## The Second Group

My second group benefitted from slightly clearer instructions. But they had all three of the insights the first group uncovered even before they started slicing or building any stories. They got hung up on other intricacies of the problem:

1. Money: The American dollars in the problem statement used a `.` to separate the integer part of a money calcuation from its decimal component. Many of the participants were used to using `,` for that purpose, so they needed to consciously second-guess every calculation output.
2. Saving: Both teams were using IDEs they weren't used to, which they hadn't set up for auto-saving. Most often an unexpected result prompted the question "Did we forget to save?"
3. Slices as defined: They got the idea of how to slice the stories. But when they got to building the solution, they had to have an "Are we really going to do it like this?" conversation. 

Just breaking down the stories wasn't where the learning happened for this team. It was the building that crystallized the gap between being able to define small pieces of work, and what it's like to actually build like that. 

They got farther in the building than my first group had, so they were able to see how adding one feature impacted the already existing ones. The big insight from this group's debrief was how one small addition affects all the existing features, and the kind of time needed to do it right and test it thoroughly. 

___

I'd love to run this workshop in other settings, but having a shared programming language and an ability to work in a strong-style pair are too big a barrier to entry to submit this as a workshop to a conference. 

How have you gotten strangers started working together on code? How have you taught (or been taught) about slicing user stories into smaller, vertical slices? 