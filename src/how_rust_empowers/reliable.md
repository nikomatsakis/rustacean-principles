# ⚙️ Reliable: "If it compiles, it works"

> One of the great things about Rust is the feeling of "it if compiles, it works". This is what allows you to do a giant refactoring and find that the code runs on the first try. It is what lets you deploy code that uses parallelism or other fancy features without exhausting fuzz testing and worry about every possible corner case.

[productive]: ./productive.md
[productivity]: ./productive.md
[supportive]: ./supportive.md
[versatility]: ./versatile.md

## In tension with

Making Rust reliable is most often at odds with making Rust feel [productive] and [supportive]. Reliability is often achieved by "cross checking", where various parts of the system check one another to ensure overall consistency. Cross checks can make it harder to make changes, since the various parts of the system must be brought in sync with one another.

Reliability can also be at odds with [versatility]. Our ability to make something reliable will always be limited. If we restrict people to only building things that whose correctness can be verified, we will limit what they can build.

## Examples

What are some of the ways that we make Rust feel **reliable**?

### [Type safety](./reliable/type_safety.md)

> Safe Rust code is guaranteed to avoid undefined behavior.

Rust programmers never have to worry about notorious, hard-to-diagnose, harder-to-fix bugs like segfaults and data races. Rust's exposure to security vulnerabilities is much reduced as a result. However, static safety comes at the cost of increased overall complexity (works against [supportive]). Figuring out the correct type annotations and other details can be difficult, working against [productivity].

### [Consider all cases](./reliable/consider_all_cases.md)

> Rust doesn't hide error conditions and encourages listing all possibilities explicitly (or acknowledging that something is elided).

Rust uses a number of mechanisms to encourage code authors to list all possibilities. This thoroughness frequently helps identify bugs because it can highlight things that the programmer has forgotten about. However, it comes at a price in [productivity], since it can force the programmer to deal with details that they haven't figure out yet. As an example, consider exhaustive matches: they are frequently very useful, but when a new enum variant is added, all matches must be edited to account for it (or else they must include a `_` case).
