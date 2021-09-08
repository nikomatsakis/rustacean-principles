# ⚙️ Reliable: "If it compiles, it works"

> One of the great things about Rust is the feeling of "it if compiles, it works". This is what allows you to do a giant refactoring and find that the code runs on the first try. It is what lets you deploy code that uses parallelism or other fancy features without exhausting fuzz testing and worry about every possible corner case.

[productive]: ./productive.md
[productivity]: ./productive.md
[supportive]: ./supportive.md
[versatility]: ./versatile.md

## In tension with

Making Rust reliable is most often at odds with making Rust feel [productive] and [supportive]. Reliability is often achieved by "cross checking", where various parts of the system check one another to ensure overall consistency. Cross checks can make it harder to make changes, since the various parts of the system must be brought in sync with one another.

Reliability can also be at odds with [versatility]. Our ability to make something reliable will always be limited. If we restrict people to only building things that whose correctness can be verified, we will limit what they can build.

## Mechanisms

What are some of the ways that we make Rust feel **reliable**?

* [Type safety](./reliable/type_safety.md): Safe Rust code is guaranteed to avoid undefined behavior.
    * *Why it makes Rust code feel reliable:* Segfaults and data races are the hardest kind of bug to diagnose and fix.
    * *Trades off:* Type safety makes the system more complex, which works against being [supportive]; it also requires the entire system to be brought into a consistent state, which can work against [productivity].
* [Consider all cases](./reliable/consider_all_cases.md): Rust doesn't hide error conditions and encourages listing all possibilities explicitly (or acknowledging that something is elided).
    * *Why it makes Rust code feel reliable:* Listing all cases often highlights things that the programmer has forgotten about.
    * *Trades off:* As with type safety, considering all cases means that the system must be brought into a consistent state, which can work against [productivity].
