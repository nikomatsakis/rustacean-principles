# ❓ FAQ

## What are these principles?

The Rust Design Principles are a proposed set of principles which guide Rust's design.

## Who developed these principles? Are they "official"?

Not yet. These principles are a work-in-progress started by [nikomatsakis] and  [joshtriplett], but incorporating feedback from many others within the Rust community.
If and when we feel the principles have reached a "settled point", we expect to create an RFC.

[nikomatsakis]: https://github.com/nikomatsakis
[joshtriplett]: https://github.com/joshtriplett

## Why is "easy to use" not one of the principles?

There are several reasons that "Easy" is not on the list of principles. The most obvious is that Rust is not, in fact, *easy*: because writing reliable, efficient, and easy to maintain programs is not easy. It requires an attention to detail.

Rust does, however, strive to be [supportive] -- we help you to learn and get started. We also strive to be [productive].

[supportive]: ./how_rust_empowers/supportive.md
[productive]: ./how_rust_empowers/productive.md
[reliable]: ./how_rust_empowers/reliable.md
[performant]: ./how_rust_empowers/performant.md

This doesn't mean we don't care about ease-of-use: of course we do!

 An inevitable consequence of prizing [reliability] and [performant] first and foremost. Nonetheless, we strive to 

*Rust puts these skills within reach, if you invest some effort* is a much much much better message than “this will be hard and you will suffer and it will be good for you”    

"we know there's a curve but we are constantly getting it as low as we can without compromising X"

This is a tricky question to answer. On the one hand, Rust has a definite learning curve, and it always will. 

We do our best to make Rust a language accessible to everyone, Rust has a definite learning curve. 
Rust is meant to be a tool that is accessible to **everyone** -- 

## Why develop these principles?

The goal of these principles is to help guide design discussions. We often find ourselves returning to the same themes over and over again, and the principles can give us a more precise vocabulary to use. We can talk about whether a feature is *supportive* or *productive*, for example. The fact that they are ordered can also help us in resolving conflicts, since we can give "the edge" to principles earlier in the list. The [case studies] enumerates several examples of this in practice.

## How can these principles be used?

These principles can guide us when having design discussions or questions of team membership. [Read more here.](./what_is_rust.md/#how-can-the-principles-be-used).