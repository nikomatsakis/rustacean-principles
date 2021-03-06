# Rust empowers by being...

Rust's [overall goal](./goals.md) is to "empower everyone to build reliable and efficient software". But how do we do that? This section identifies the various things that Rust tries to be in order to empower its users. If you click on a particular entry, you will find more notes, along with a list of mechanisms that we use (for example, reliability is enhanced by type safety).

**Note that these goals are often in tension.** For any given design, we always want to achieve (or at least be neutral) all of these feelings. In some cases, though, we may be forced to decide between slightly penalizing one goal or another. In that case, we tend to support those goals that come earlier in the list over those that come later (but every case is different). See the [case studies](./case_studies.md) for examples.

## [⚙️ Reliable](./how_rust_empowers/reliable.md): "if it compiles, it works"

> One of the great things about Rust is the feeling of "it if compiles, it works". This is what allows you to do a giant refactoring and find that the code runs on the first try. It is what lets you deploy code that uses parallelism or other fancy features without exhausting fuzz testing and worry about every possible corner case.

## [🐎 Performant](./how_rust_empowers/performant.md): "idiomatic code runs efficiently"

> In Rust, the fastest code is often the most high-level: convenient features like closures, iterators, or async-await map down to code that is at once efficient and which uses minimal memory.

## [🥰 Supportive](./how_rust_empowers/supportive.md): "the language, tools, and community are here to help"

> We strive to make our tools polished and friendly, and we look for every opportunity to guide people towards success. Part of that is building a community that eagerly shares its knowledge in a welcoming and inclusive way.

## [🧩 Productive](./how_rust_empowers/productive.md): "a little effort does a lot of work"

> Rust and its ecosystem offer a wide array of powerful building blocks that can be combined and recombined. The result is that standing up a quality system can be done in record time.

## [🔧 Transparent](./how_rust_empowers/transparent.md): "you can predict and control low-level details"

> The translation from Rust to underlying machine code is straightforward and predictable. If needed, you have options to control the low-level details of how your application works.

## [🤸 Versatile](./how_rust_empowers/versatile.md): "you can do anything with Rust"

> Rust scales well both up and down: it is well-suited to building everything from simple scripts to web servers to WebAssembly programs to kernel extensions and embedded systems. It is usable on both common and esoteric platforms.
