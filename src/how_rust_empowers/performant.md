# 🏇 Performant: "idiomatic code runs efficiently"

> In Rust, the fastest code is often the most high-level: convenient features like closures, iterators, or async-await map down to code that is at once efficient and which uses minimal memory.

## In tension with

Making Rust feel performant can be in tension with Rust feeling [supportive], and in some cases [productive]. The problem is that making abstractions efficient may mean that they aren't able to provide some of the niceties that users are accustomed to from other languages. Less obvious is that feeling performant can be in tension with feeling [transparent] or [versatile]; this is because many optimizations rely on a lack of transparency about the precise order or way in which things happen, and having more visibility, or more choices, can make those optimizations harder to do.

[supportive]: ./supportive.md
[productive]: ./productive.md
[versatile]: ./versatile.md
[transparent]: ./transparent.md

## Examples

What are some of the ways that we make Rust feel **performant**?

### [Zero-cost abstractions](./performant/zca.md)

Rust iterators are a good example of something which meets our goal of being *performant*. Code that uses iterators not only feels higher-level, it often compiles down to loops which are more efficient than if you wrote the loops with explicit iterators. This is because iterators are able to skip bounds checks on vectors or take other shortcuts.

> "What you don't use, you don't pay for. And further: What you do use, you couldn't hand code any better." -- Bjarne Stroustroup

### [Specify only what's necessary](./specify_only_what_is_necessary.md)

> Specify the details that are needed to capture the programmer's intent, but not more.

Many details of Rust are left deliberately unspecified. For example, unless users manually add a `repr` attribute, Rust structs and enums can be laid out in memory however the compiler sees fit. This allows us make optimizations like reordering struct fields to eliminate padding and reduce size, or representing `Option<&T>` as a single, nullable pointer. (Of course, reserving this freedom works against [transparency] and [versatility], which is why we have the option to specify the `repr`.)
