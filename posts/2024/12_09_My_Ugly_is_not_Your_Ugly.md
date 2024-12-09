.. title: My Ugly is not Your Ugly
.. date: 9 December 2024
.. description: 
.. tags: code-review, automation, doubt, feedback, handoff, mindset, typescript, testing
.. previewimage: /images/posts/2024/ugly-fish.jpg

Ugly code can mean lots of things: code someone else wrote, code with inconsistent white space placement, code that takes up too many lines, code that requires too many command + clicks to parse, code that looks redundant. 
I was struggling with the last of these recently. To me, some code a colleague wrote looked redundant. And vice versa, they thought code I wrote was unnecessarily duplicated.

They’d built an API client for our new (weeks-old) test automation suite. It had everything the API client had in the old suite: an endpoint for each HTTP verb, error handling, headers and data abstracted, logging the request and response. Plus it had an assert on the status code. It used a library to make the API calls. 

I’d written my test without using my colleague's API client. I’d called a different library directly. This library logged about ~30 lines of request and response when the test failed, little enough that I didn’t have to scroll too much. The expected line appeared in green and the actual line appeared in red, among the grey request and response in my IDE’s syntax highlighting. By comparison, my colleague's API client logged the request and response for success and failure, but the library it called logged ~200 lines of output with four colors. 

To me, using the API client was ugly. It was extra clicks to see what it was doing from the test, it was extra code in the code base, and it was extra output lines to scroll through and understand when my test failed. To me, it looked like extra. 

But to my colleague, my code looked like extra. For every API call, I set up the headers, and for POST calls the data too. I had a line that verified the status code, and a line that converted the data in the response into a JSON object. To their developer brain, lines of repeated code should be abstracted away. 

For my tester brain, when I see a test fail and the output tells me the failure happened in an abstraction, I want to scream. I want the IDE to point me to the exact line of the failure. I don’t just want to know that something went wrong with an API call, I want to know which one in the context of the test so I can properly diagnose the issue without scrolling through piles of logs. 

![](/images/posts/2024/ugly-fish.jpg "Is this fish uglier than your code?")

I wanted to remove the API client completely. I started the conversation in Slack with screenshot comparisons of the different libraries outputs. I had a conversation with a couple people who'd been reviewing my code. They seemed fine to merge my couple of tests without the API client, but still wary about how ugly the code was. 

I sought an expert opinion from my colleague Arjan Blok, who has deep experience in test automation and no experience in our weeks-old code base or the application it was testing. He asked a clarifying question that pulled me back to using API client: "What would be different in each call?" It's true that I didn't need the headers and data setup to be visible in the test. They could take up part of one line instead of 5-10. 

Arjan also pointed out the tests weren't all following the arrange-act-assert pattern. The tests using my colleague's API client had the asserts in the test. This is what looked ugly to me, not the idea of an API client itself!

I set up one POST call in a new method of the API client and returned the response body. I pulled the code up at standup with the whole group to explain why I was back on board with the API client idea, but  interested in seeing it develop a bit differently. The other tester and myself were able to explain to the developers in the group why it's valuable to have the assert in a test. The developers in the group had a chance to explain why the asserts in the tests felt like duplicates. 

Being specific about what was ugly to each of us helped us come to a compromise about the API client. We're keeping the headers and data abstracted (so my tests need to change) but moving the asserts (so my colleague's tests need to change). We seemed to all agree to write at the same level of abstraction going forward, but of course only time will tell!

---

For the book club I run in our R&D department, we’re currently reading [The Programmer’s Brain](https://www.manning.com/books/the-programmers-brain) by Felienne Hermans. It tackles what makes code "readable" or "ugly": what’s in short term vs. long term memory of your brain, how you read code, what makes for higher cognitive load, and how to get past the point of looking up syntax on Stack Overflow all the time. 

I find it disorienting to click through to different abstraction layers in a new code base in a new language. The same for scrolling through a bunch of test output, not having the assert in the test -- I feel lost. For my colleague who wrote the API client, scrolling through a bunch of tests with lots of lines they didn't write was disorienting. They couldn't get an overview of what all was being tested. 

I guess the moral of this story is: tell your colleagues *what* about their code is ugly, and [show your work](https://elizabethzagroba.com/posts/2017/2017-08-06_doubt-builds-trust/), even if it's ugly. Maybe they'll both change. 

---

Photo by <a href="https://unsplash.com/@gouthr?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Bobby Mc Leod</a> on <a href="https://unsplash.com/photos/a-close-up-of-a-fish-on-a-rock-NP5jSo6OcXI?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
