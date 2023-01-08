.. title: I don't know, let's look together.
.. date: 19 December 2022
.. tags: mindset, leadership, python, debugging
.. description: Modelling a beginner's mindset as a leader

A few weeks ago, something was failing. My colleague didn't know why. They reached out to me. I've copied our Slack conversation mostly verbatim, with a bit a cleanup for typos. 

Here's how it began: 

> developer [11:35 AM]
Hi Elizabeth, do you by any chance have experience with pytest exit codes in gitlab ci? {link to pipeline job output} this job on on line (316) runs pytest, and the test fails. I would expect to get an exit code 1, but as seen on line 390 it is 0.

So many good things here already. They've asked about my experience before assuming I don't have any. They've linked to the pipeline job so I can read the error message in context myself. They've also summarized what their expected behavior should be, and what the actual behavior was.

> ez  [11:37 AM]
not really, but i thought those exit codes were a bash thing, not a python thing {[link to stack overflow](https://stackoverflow.com/questions/67082939/gitlab-ci-ignores-script-exit-code-other-than-1)}

I stated up front that I didn't have the answer. This gives my developer a chance to bail immediately, in case they know a more qualified but less available expert. I used safety language ("I thought" vs. stating a fact) to reinforce that I could be wrong, but link to my source so my developer can judge for themselves.

> developer  [11:39 AM]
pytest does describe them here [https://docs.pytest.org/en/7.1.x/reference/exit-codes.html](https://docs.pytest.org/en/7.1.x/reference/exit-codes.html)

> developer [11:40 AM] gitlab indeed by default exits on error, which can be disabled with set +e

The developer has found (and read) an even better reference, the documentation for the pytest library, huzzah! That definitely trumps my Stack Overflow link. Now it's clear which reference to use. They've also brought us one step further along in the troubleshooting process, introducing the `+e` as a potential exit code helper to overwrite whatever pytest is doing. 

> ez  [11:40 AM]
huh, guess you know more than i do!

Recognition! Not exactly praise here, but I admit that they are more informed and on a better track. Celebrating when you're wrong and the developer's right helps build credibility and rapport for the next time when it's the other way around. 

Now I want to meet them where they are, and get them one step further. 

> ez  [11:46 AM]
can i give you a call? i’m trying to figure out if the code is being logged in the wrong spot, or if gitlab isn’t responding to the code correctly.

> developer  [11:47 AM] yes sure

> Zoom  [11:47 AM] Call
 | Zoom meeting started by elizabeth.zagroba | Ended at 11:55 AM - Lasted 8 minutes | 2 people joined

I've spent a few minutes Duck Duck Go-ing and reading about the issue. I've got more links I've got pulled up in my browser, but rather than continuing to chat links and theories back and forth, I wonder if calling the developer will get this solved by lunchtime at noon. 

> ez  [11:50 AM]
[https://gitlab.com/gitlab-org/gitlab/-/issues/340390](https://gitlab.com/gitlab-org/gitlab/-/issues/340390)


I don't have the recording of the meeting, but the last message I sent the developer was while we were on the Zoom. I put the link in the Slack chat so it wouldn't be lost to time or browser history after we hung up. 

My theory about the exit code was on the right track. The developer assumed that if pytest exited with a 1 or a 0 on line 174, the bash script on line 175 would know that already. It didn't. We had to collect the exit code on line 174. 

---

Only the last little piece, about needing to collect the exit code on the same line the command is executed, was new information. This technical bit was the only thing I learned that day. The rest I knew, and am grateful for: 

- Ask people about their experience before diving into an explanation.
- Describe what you've tried already.
- [Admit when you don't know something](https://elizabethzagroba.com/posts/2017/2017-08-06_doubt-builds-trust/), or describe how deep your knowledge is. (And be kind to people who make themselves vulnerable in this way.)
- Link to the thing so your pair can see what you're talking about for themselves. 
- Celebrate the good things. 
- When the communication format is getting in the way, try something else. 

I would definitely pair with this developer again, on any problem, whether or not I knew the answer. Every day should be so great. 