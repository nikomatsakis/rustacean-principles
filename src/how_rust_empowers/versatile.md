# 🤸 Versatile: "you can do anything with Rust"

> Rust scales well both up and down: it is well-suited to building everything from simple scripts to web servers to WebAssembly programs to kernel extensions and embedded systems. It is usable on both common and esoteric platforms.

## In tension with...

Feeling versatile can be in tension with feeling [supportive] and [productive].

[supportive]: ./supportive.md
[productive]: ./productive.md

## Mechanisms

What are some of the ways that we make Rust feel **versatile**?

### Expose all system capabilities

We aim to expose all the core system capabilities to Rust programs in some way, even if accessing them or using them correctly can be difficult. We don't want Rust users to feel they have to "drop down" to C or some other language; they should be able to use unsafe Rust to get their job done. Features like "inline assembly" are following in this vein.

An example of this mechanism in action is `repr(C)`. Although our default struct layout is not defined ()