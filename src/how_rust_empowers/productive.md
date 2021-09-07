# 🧩 Productive: "a little effort does a lot of work"

> Rust and its ecosystem offer a wide array of powerful building blocks that can be combined and recombined. The result is that standing up quality code can be done in record time.

## In tension with

Making Rust feel productive can be in tension with Rust feeling [reliable] and, in some cases, [performant].

[reliable]: ./reliable.md
[performant]: ./performant.md

## Mechanisms

What are some of the ways that we make Rust feel **productive**?

### Enable a flourishing ecosystem

### Stability; editions

Rust has a [commitment to stability](https://blog.rust-lang.org/2014/10/30/Stability.html) across versions. This is because stability is a key enabler of productivity: without stability across versions, you are forced to spend time resolving build failures instead of building the functionality you want to build.

Stability however can work against any of the various feelings that we strive for by giving us less "degrees of freedom" in our designs. The goal of Rust's editions system is too help finesse that tradeoff. Rust Editions permit us to make what would otherwise be breaking changes; because using the new edition is opt-in, and editions are interoperable, people can choose to adopt the newer behavior on their own schedule, thus avoiding the hit to productivity.

### rustfmt



### Portability

Rust code aims to be portable across all mainstream architectures by default.
