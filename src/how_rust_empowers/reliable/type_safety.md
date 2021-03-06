# Type safety (but with an unsafe escape hatch)

> Safe Rust code is guaranteed to avoid undefined behavior.

Type safety is a key element to reliability. We ensure that safe Rust code is free of "undefined behavior", which is the term that compiler authors use to refer to things like segfaults, data races, and out-of-bounds memory accesses.

Type safety is not a suggestion: we don't accept **almost safe** APIs, which are safe so long as you don't do "unreasonable" things. For example, we would not accept a safe API that avoids undefined behavior so long as no cycles exist between ref-counted objects. Reasonable people do "unreasonable" things in code all the time, either because they don't yet know what is reasonable or not, or because the complexity of the system gets away from them. The role of the compiler is to manage that for you.

However, type safety carries a cost, too. It adds complexity, which can work against Rust feeling [productive]. It also makes Rust more complex and hard to learn, which can work against feeling [supportive] -- we work hard on our error messages and documentation precisely to help mitigate this cost. Precisely because of these costs, we have imposed some limits on what Rust's type system tries to achieve:

* We employ **runtime checks** for certain kinds of error conditions. For example, we do not try to prove that indexes are within bounds, but instead check an expression like `vec[i]` to ensure that `i < vec.len()`. Proving conditions about the specific value of a variable (in this case, `i` or the length of a vector) would be a "big step up" in complexity of the type system. Rust's choice not to do so decreases that feeling of reliability, but with massive benefits to [productivity].
* We permit **unsafe code**, which gives authors an escape hatch from the type system. This means that we can support many kinds of systems programming patterns while keeping the type system itself relatively simple. (For example, the system of ownership and borrowing cannot express doubly linked lists, but they can be implemented with unsafe code.)
    * However, we do expect authors to **encapsulate** their unsafe code, presenting a safe interface to the world at large. This works against the feeling of [productivity] for unsafe code authors (it's more complex to think about how to encapsulate things) but with great benefits for reliability for the rest of the world.
