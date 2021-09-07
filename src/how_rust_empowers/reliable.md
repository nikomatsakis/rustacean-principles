# ⚙️ Reliable: "If it compiles, it works"

> One of the great things about Rust is the feeling of "it if compiles, it works". This is what allows you to do a giant refactoring and find that the code runs on the first try. It is what lets you deploy code that uses parallelism or other fancy features without exhausting fuzz testing and worry about every possible corner case.

[productive]: ./productive.md
[productivity]: ./productive.md
[supportive]: ./supportive.md

## In tension with

Making Rust reliable is most often at odds with making Rust feel [productive] and [supportive]. Reliability is often achieved by "cross checking", where various parts of the system check one another to ensure overall consistency. Cross checks can make it harder to make changes, since the various parts of the system must be brought in sync with one another.

## Mechanisms

What are some of the ways that we make Rust feel **reliable**?

### Type safety (but with an unsafe escape hatch)

*Makes Rust code feel **reliable** but can work against Rust feeling [productive] and [supportive].*

Type safety is a key element to reliability. We ensure that safe Rust code is free of "undefined behavior", which is the term that compiler authors use to refer to things like segfaults, data races, and out-of-bounds memory accesses.

Type safety is not a suggestion: we don't accept **almost safe** APIs, which are safe so long as you don't do "unreasonable" things. For example, we would not accept a safe API that avoids undefined behavior so long as no cycles exist between ref-counted objects. Reasonable people do "unreasonable" things in code all the time, either because they don't yet know what is reasonable or not, or because the complexity of the system gets away from them. The role of the compiler is to manage that for you.

However, type safety carries a cost, too. It adds complexity, which can work against Rust feeling [productive]. It also makes Rust more complex and hard to learn, which can work against feeling [supportive] -- we work hard on our error messages and documentation precisely to help mitigate this cost. Precisely because of these costs, we have imposed some limits on what Rust's type system tries to achieve:

* We employ **runtime checks** for certain kinds of error conditions. For example, we do not try to prove that indexes are within bounds, but instead check an expression like `vec[i]` to ensure that `i < vec.len()`. Proving conditions about the specific value of a variable (in this case, `i` or the length of a vector) would be a "big step up" in complexity of the type system. Rust's choice not to do so decreases that feeling of reliability, but with massive benefits to [productivity].
* We permit **unsafe code**, which gives authors an escape hatch from the type system. This means that we can support many kinds of systems programming patterns while keeping the type system itself relatively simple. (For example, the system of ownership and borrowing cannot express doubly linked lists, but they can be implemented with unsafe code.)
    * However, we do expect authors to **encapsulate** their unsafe code, presenting a safe interface to the world at large. This works against the feeling of [productivity] for unsafe code authors (it's more complex to think about how to encapsulate things) but with great benefits for reliability for the rest of the world.

### Consider all cases

Rust generally aims to make sure that you 'acknowledge' or consider all cases. You can see this in `match` statements, which require exhaustive matching (many other languages permit you to leave off match arms that you believe cannot occur); when matching, we also require that users list all fields in a struct, or acknowledge (with `..`) that they have not done so. Forcing users to consider all cases helps make Rust feel reliable, but it can come at the cost of feeling [productive]. This is why we frequently pay careful attention to the details of 

A good case study for the tradeoffs involved is error handling. The traditional approach to error handling for a long time was exceptions. Exceptions are great for feeling [productive], as they allow errors to quietly pass through any amount of code. However, the result is a proliferation of hidden control-flow paths that are very hard to reason about. In practice, recovering from exceptions is fraught with error, and hence they work against the feeling of reliability. The problem is that typical mechanisms such as returning an error code are also not reliable; it's too easy to forget to check for an error.

Rust instead adopts the approach pioneered in functional languages of returning an enum. The `Result` enum allows one to signal an error in a way that *forces* the error to be considered. Still, the most common way to handle an error is to propagate it to your caller, and in order to feel productive, it's important that this operation be *concise*. Rust's `?` operator was added to restore productivity while ensuring that error paths are still visible to users and are not completely overlooked.

### Cargo's dependency system

Cargo's dependency system is geared towards reproducible builds. Once an application builds, the `Cargo.lock` file ensures that you don't get surprised by new versions of dependencies that you didn't request.

### Explicit error handling with `?`

Rust eschews exceptions in their traditional form, instead preferring to leverage `Result` types. The `?` operator is at once concise and visible, making it possible to see where errors occur without obscuring the "happy path" where the code is successful. The `?` operator also enables "error type adaptation", which is an example of [polish](./polish.md).

**Too little:** Exceptions that invisibly propagate across stack frames. Experience has shown that programmers have a hard time ensuring that the state of their program is consistent after exceptions are thrown (this is why Rust panics are reserved for irrecoverable error conditions).

**Too much:** Requiring a lot of ceremony on each error could make programs more reliable, but would work against [empowering](./empowering.md) or [polished](./polished.md). 

