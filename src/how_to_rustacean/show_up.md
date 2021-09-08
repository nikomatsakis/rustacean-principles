# 👋 Show up

> Bring your expertise and be willing to argue for what you think is right.

There are a few key points here:

* You have to have a good sense of what you know and what you don't.
* If you see people making a mistake, and it's about an area that you know, don't be afraid to point it out.
* People don't always understand the first time, so sometimes you have to stick with it a bit.

At the same time:

* If you are going to raise an objection, you have to be willing to make your case. You can't raise concerns and block indefinitely.
* It may well be that others *do* understand your point, but just don't agree about how important it is. Ultimately, you have to [trust] that others have the best interest of Rust at heart, too.
* The hardest disagreements to resolve often have underlying disagreements in values or the priorities of those values. Resolving such disagreements in an ideal way often requires introspecting on your own values, and understanding and empathizing with the values of others.

[trust]: ./trust_and_delegate.md

## Examples

### Raising an objection about a design

You are a member of the Rust lang team and you are concerned about the proposed syntax for a design.

**Just right (and you convince the others):** You raise the objection and make your case for why the syntax is wrong. At first, nobody seems to understand the point you are making, but they extend some trust that you may have a valid point. You try again, this time explaining it from a different angle, and trying to understand and bridge the gap to other people's perspectives and values. This time, it works, and a few members of the team see what you're getting at. After a few more days of discussion, the consensus has shifted, possibly to your proposal or possibly to a new solution that satisfies everyone.

**Just right (and you don't):** You raise the objection and make your case for why the syntax is wrong. At first, nobody seems to understand the point you are making, so you try again, this time explaining it from a different angle. Still, the other members of the team don't agree. They are able to repeat back what you said, including the values you hold that it relates to, and they seem to understand it. but they just don't feel the problem will be as serious as you do, or they feel it's outweighed by other concerns of comparable value and there isn't a solution that satisfies everything. (We should hesitate to select "satisficing" solutions, but sometimes they may be necessary.) At that point, you release your objection. You record a "dissenting opinion", and that opinion is reflected in the "unresolved questions" of subsequent tracking issues, for later re-evaluation before stabilization.

**Too much (blocking progress):** You raise your objection but the rest of the team doesn't seem to agree. You insist that they are wrong and block progress. The team doesn't understand your position and values, and/or you don't understand theirs, so people talk past each other or don't talk at all. Eventually, the whole feature is dropped out of frustration.

**Not enough (giving up too easily):** You raise the objection and make your case for why the syntax is wrong. There is some pushback, and you feel pressure or discomfort maintaining your objection, so you give up and withdraw your concern. Sure enough, though, when the feature is released, the syntax proves to be a major obstacle. You wish you had made your case a bit more forcefully. The overall process would benefit from "forceful" not being a required property of a well-reasoned objection, and would benefit from recording the objection for further examination later in the process.

**Not enough ([cookie licking]):** You leave a comment on the issue stating that you have concerns, but you refuse to engage and discuss them in detail. "I object to this course of action, but I don't have time to get into it right now, and I don't when I will." This does not mean you're wrong for not having the time or energy to get into it, but rather that the process of making a blocking objection requires someone to take the time and energy to explain, discuss it with other members of the team, and convince others; that's part of the expectations from a team member.

[cookie licking]: https://devblogs.microsoft.com/oldnewthing/20091201-00/?p=15843
