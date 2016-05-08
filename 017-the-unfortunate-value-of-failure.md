### The Unfortunate Value of Failure

_Ramsey Nasser_

As developers we fail all the time, and it feels bad.

Failure is irrevocably linked to surprise. Failure always happens when something happens that we did not expect. Therefore, failure is always linked to new information.

Yet failure feels terrible. Why? Part of the reason is the way we approach it in programming. All the UX of errors in most programming environments emphasize red, a stop sign, an exclamation point, basically very negative things.

We also have a culture in programming of harping on errors as the programmer's fault.

< Ramsey walks us through a person on StackOverflow who only posts answers that are one sentence followed by "Stop doing that" >

These responses are worse than no response at all. They'll drive people to stop doing programming.

< Ramsey posts some of Elm's error messages, which not only are detailed but automatically include a rationale for why the program is incorrect >

Most computer failures are due to the machine needing more information to keep on going. The state space of programming is huge -- there's no way for humans to reason about the way programs holistically work. We have to focus on only a few things at a time.

< example of the state space of the add function in C >

This is also why reproducibility is hard.

When programming we're always doing something new -- we don't write the same program over and over again. That is why programming is prone to failure.

< Ramsey has an excerpt from the movie Amadeus where Mozart's rival is shocked to read his manuscripts and sees there are no corrections; the music is perfect, as if Mozart was just writing it down, fully formed >

We don't program by taking dictation from God. We have to make corrections.

If you don't fail 90% of the time you're not aiming high enough. -Alan Kay

Anxiety as a programmer is the difference between what you're trying to do and your skill. But part of growing as a programmer is doing harder and harder things. If Ramsey just kept making websites every day, he'd probably feel pretty confident in himself, but he wouldn't be growing as much. Now he works on compilers. He still feels terrible, but he's objectively better as a programmer than he was.

Failure is learning + growth. It's not something you did wrong.

Some takeaways:
* Tools need better error messages. This is actually a really hard problem; the way many tools are written makes it very difficult for the tool author to report more information to the user. Tools need to be built from the ground up with rich error messages in mind.
* More safe spaces for failure.
* Teachers: fail in front of students. Don't give people the image of a good programmer as Mozart descending from the clouds with perfect music. Note that this is easier for men to do; if a woman is publicly failing at programming she's likely to get shot down a lot faster than a man would. This is part of why safe spaces are so important.
