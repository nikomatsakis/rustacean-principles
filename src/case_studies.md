# Case studies

What follows are a list of short examples of elements of Rust's design. For each one, we elaborate on some of the 

Key:

* 💚 -- strong improvement
* 🟡 -- mildly better or mildly worse
* ❌

## Type safety, unsafe code, and verification: a delicate balance

| Feature     | Reliable | Performant | Productive | Supportive | Transparent | Versatile |
| ----------- | -------- | ---------- | ---------- | ---------- | ----------- | --------- |
| Type safety | 😎      |            | 😎        |            | 😓         | 😓       |

## The `?` operator: a delicate balance

| Feature          | Reliable | Performant | Productive | Supportive | Transparent | Versatile |
| ---------------- | -------- | ---------- | ---------- | ---------- | ----------- | --------- |
| The `?` operator | 💚      | 🟡        | 🟡        | 🟡        | 💚         | 💚       |

## Coherence: a key feature, but one perhaps ready to be revisited

| Feature   | Reliable | Performant | Productive | Supportive | Transparent | Versatile |
| --------- | -------- | ---------- | ---------- | ---------- | ----------- | --------- |
| Coherence | 💚      |            | 💚        |            | ❌         | ❌       |

Rust's ["coherence rules"](https://doc.rust-lang.org/reference/items/implementations.html?highlight=coherence#trait-implementation-coherence) are limits on the sets of impls that people are allowed to write in their crates. The goal is to ensure that, no matter what crates you grab from crates.io and add to your dependency list, there is also a consistent (one might say "coherent") set of impls -- and we never have the problem where there are two different `Hash` impls defined for a given type (for example). Those kinds of situations can lead to subtle bugs or other errors.

These rules serve an essential function, but they can also be severely limiting and a source of frustration. They are probably a good example of a language feature that ought to be adjusted, because of their severe impact on versatility and transparency (but which cannot be removed entirely, because they are needed for reliability and productivity).

**😎 Productive:** It may surprise you to hear coherence described as a win for producitivity, given that it *prevents* you from writing impls you might have otherwise liked to write (and indeed this is reflected in its impact on versatility). The reason that coherence helps productivity is because the rules are setup to ensure that any two crates on crates.io can be combined without linker errors or surprising behavior. 

**😎 Reliabie:** Coherence 

