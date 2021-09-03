# 🏇 Performant: "ran well right out of the box"

> > In Rust, the fastest code is often the most high-level: convenient features like closures, iterators, or async-await map down to code that is at once efficient and which uses minimal memory.

## Examples

### Iterators

Rust iterators are a good example of something which meets our goal of being *performant*. Code that uses iterators not only feels higher-level, it often compiles down to loops which are more efficient than if you wrote the loops with explicit iterators. This is because iterators are able to skip bounds checks on vectors.

### Async-await

The goal with async-await syntax is to make a convenient, accessible way to write code which compiles down to the same sort of state machines that C programmers have been writing by hand to create event-driven architectures.