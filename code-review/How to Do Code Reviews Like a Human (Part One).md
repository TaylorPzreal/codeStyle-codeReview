# How to Do Code Reviews Like a Human (Part One)

> From [https://mtlynch.io/human-code-reviews-1/](https://mtlynch.io/human-code-reviews-1/)

Lately, I’ve been reading articles about best practices for code reviews. I notice that these articles focus on finding bugs to the exclusion of almost every other component of a review. Communicating issues you discover in a constructive and professional way? Irrelevant! Just identify all the bugs, and the rest will take care of itself.

So I had a revelation: if this works for code, why not romance? With that, I’m announcing my new ebook to help developers with their love lives:

My revolutionary ebook teaches you proven techniques for maximizing the number of deficiencies you find in your partner. The ebook does not cover:

Communicating issues to your partner with empathy and understanding.
Helping your partner address their weaknesses.
Based on my reading of code review literature, those parts of a relationship are obvious and not worth discussing.

Does this sound like a good ebook to you? I’m assuming you just yipped “Nonononono!”

So, why is that the way we talk about code reviews?

I can only assume the articles I’ve read are from the future, where all developers are robots. In that world, your teammates welcome thoughtlessly-worded critiques of their code because processing such information warms their cold, robot hearts.

I’m going to make the bold assumption that you want to improve code reviews in the present, where your teammates are humans. I’ll make the even bolder assumption that a positive relationship with your colleagues is an end in itself and not simply a variable you adjust to minimize your cost-per-defect. How would your review practices change under these circumstances?

In this article, I discuss techniques that treat the code review as not only a technical process but a social one as well.

What is a code review?

The term “code review” can refer to a range of activities, from simply reading some code over your teammate’s shoulder to a 20-person meeting where you dissect code line by line. I use the term to refer to a process that’s formal and written, but not so heavyweight as a series of in-person code inspection meetings.

How to Do Code Reviews Like a Human (Part One)

October 12, 2017
 19 minute read
Lately, I’ve been reading articles about best practices for code reviews. I notice that these articles focus on finding bugs to the exclusion of almost every other component of a review. Communicating issues you discover in a constructive and professional way? Irrelevant! Just identify all the bugs, and the rest will take care of itself.

So I had a revelation: if this works for code, why not romance? With that, I’m announcing my new ebook to help developers with their love lives:

 ebook cover

My revolutionary ebook teaches you proven techniques for maximizing the number of deficiencies you find in your partner. The ebook does not cover:

Communicating issues to your partner with empathy and understanding.
Helping your partner address their weaknesses.
Based on my reading of code review literature, those parts of a relationship are obvious and not worth discussing.

Does this sound like a good ebook to you? I’m assuming you just yipped “Nonononono!”

So, why is that the way we talk about code reviews?

I can only assume the articles I’ve read are from the future, where all developers are robots. In that world, your teammates welcome thoughtlessly-worded critiques of their code because processing such information warms their cold, robot hearts.

I’m going to make the bold assumption that you want to improve code reviews in the present, where your teammates are humans. I’ll make the even bolder assumption that a positive relationship with your colleagues is an end in itself and not simply a variable you adjust to minimize your cost-per-defect. How would your review practices change under these circumstances?

In this article, I discuss techniques that treat the code review as not only a technical process but a social one as well.

What is a code review?

The term “code review” can refer to a range of activities, from simply reading some code over your teammate’s shoulder to a 20-person meeting where you dissect code line by line. I use the term to refer to a process that’s formal and written, but not so heavyweight as a series of in-person code inspection meetings.

 Code review flow

The participants in a code review are the author, who writes the code and sends it for review, and the reviewer, who reads the code and decides when it’s ready to be merged in to the team’s codebase. A review can have multiple reviewers, but I assume for simplicity that you are the sole reviewer.

Before the code review begins, the author must create a changelist. This is a set of changes to source code that the author wants to merge in to the team’s codebase.

A review begins when the author sends their changelist to the reviewer. Code reviews happen in rounds. Each round is one complete round-trip between the author and reviewer: the author sends changes, and the reviewer responds with written feedback on those changes. Every code review has one or more rounds.

The review ends when the reviewer approves the changes. This is commonly referred to as giving LGTM, shorthand for “looks good to me.”

Why is this hard?

If a programmer sends you a changelist that they think is awesome, and you write them an extensive list of reasons why it’s not, that’s a sensitive message to get across.

That’s one reason I don’t miss IT, because programmers are very unlikable people… In aviation, for example, people who greatly overestimate their level of skill are all dead.

-Philip Greenspun, co-founder of ArsDigita, excerpted from Founders at Work

It’s easy for an author to interpret criticism of their code as an implication that they are an incompetent programmer. Code reviews are an opportunity to share knowledge and make informed engineering decisions. But that can’t happen if the author perceives the discussion as a personal attack.

As if this wasn’t difficult enough, you also have the challenge of conveying your thoughts in writing, where the risk of miscommunication is higher. The author can’t hear your tone of voice or see your body language, so it’s even more important to articulate your feedback carefully. To an author who’s feeling defensive, an innocuous note like, “You forgot to close the file handle,” can read as, “I can’t believe you forgot to close the file handle! You’re such an idiot.”

Techniques

Let computers do the boring parts
Settle style arguments with a style guide
Start reviewing immediately
Start high level and work your way down
Be generous with code examples
Never say “you”
Frame feedback as requests, not commands
Tie notes to principles, not opinions
Let computers do the boring parts
Between interruptions like meetings and emails, the time you have available to focus on code is scarce. Your mental stamina is in even shorter supply. Reading a teammate’s code is cognitively taxing and requires a high level of concentration. Don’t squander these resources on tasks a computer can do, especially when a computer can do them better.

Whitespace errors are an obvious example. Compare how much effort it takes for a human reviewer to find an indenting mistake and work with the author to correct it as opposed to just using an automated formatting tool:

Reviewer searches for whitespace issues and finds incorrect indentation.
Reviewer writes a note calling out the incorrect indentation.
Reviewer rereads their note to make sure that it's worded in a clear, non-accusatory way.
Author reads the note.
Author corrects the code indentation.
Reviewer verifies that the author addressed their note properly.