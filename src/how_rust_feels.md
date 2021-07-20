# How Rust ought to feel

This section identifies the way that Rust ought to feel, when everything is going right. These are the goals by which we evaluate new features.

## Reliable: "if it compiles, it works"

One of the great things about Rust is the feeling of "it if compiles, it works". This is what allows you to do a giant refactoring and find that the code runs on the first try. It is what lets you deploy code that uses parallelism or other fancy features without exhausting fuzz testing and worry about every possible corner case.

## Performant: "ran well right out of the box"

Rust code tends to perform "quite well" right out of the box. You don't have to give up the "nice things" in the language, like closures or high-level APIs, in order to get good performance and tight memory usage. In fact, those high-level APIs often perform as well or better than what you would get if you wrote the code yourself.

## Empowering: "complex stuff feels easy"

Rust's great strength is taking formerly complex, wizard-like things and making them easy to do. In the case of async, that means letting people use the latest and greatest stuff, like io-uring. It also means enabling parallelism and complex scheduling patterns very easily.

## Transparent and tunable: "it's easy to understand what code will do when it runs"

## Consistent: "Rust is coherently designed"

Rust has a lot of parts, but they fit nicely together. As you learn more about how each feature of Rust works, you 

## Productive: "great crates for every need, just mix and match"

## Control: "I can do all the weird things"

## Interoperable: "integrating with C++, node.js, etc is easy"
