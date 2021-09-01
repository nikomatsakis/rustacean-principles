# How Rust ought to feel

This section identifies the way that Rust ought to feel, when everything is going right. These are the goals by which we evaluate new features.

## [Reliable](./how_rust_feels/reliable.md): "if it compiles, it works"

> One of the great things about Rust is the feeling of "it if compiles, it works". This is what allows you to do a giant refactoring and find that the code runs on the first try. It is what lets you deploy code that uses parallelism or other fancy features without exhausting fuzz testing and worry about every possible corner case.

## [Performant by default](./how_rust_feels/performant.md): "idiomatic code runs efficiently"

> Rust code tends to perform "quite well" right out of the box. You don't have to give up the "nice things" in the language, like closures or high-level APIs, in order to get good performance and tight memory usage. In fact, those high-level APIs often perform as well or better than what you would get if you wrote the code yourself.

## [Productive](./how_rust_feels/productive.md): "just a few lines of code can do a lot of work"

> Rust offers a lot of 'best in class' crates that make it easy to get things up and going. Cargo

## [Polished](./how_rust_feels/polished.md): "Rust gets the big *and* the small things right"

> Rust is built with an attention to detail. Whether it's the error messages, the tooling, or the details of the type system, we try to 

## [Versatile](./how_rust_feels/versatile.md): "whatever it is I want to do, I can use Rust to do it"

> Rust can be used to build everything from simple scripts to web servers to WebAssembly programs to kernel extensions and embedded systems. Rust works consistently on all major  platforms -- and a lot of minor ones -- and exposes all system capabilities. Rust's lack of runtime and native support for the C ABI mean that you can use it to "plug in" to existing systems just like you would with a C library.