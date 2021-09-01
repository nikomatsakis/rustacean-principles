# ⚙️ Reliable: "If it compiles, it works"

> One of the great things about Rust is the feeling of "it if compiles, it works". This is what allows you to do a giant refactoring and find that the code runs on the first try. It is what lets you deploy code that uses parallelism or other fancy features without exhausting fuzz testing and worry about every possible corner case.

## Examples

### Type safety, but with an unsafe escape hatch

All Rust code follows a strict safety guarantee: no undefined behavior without using unsafe code. This provision aims to strike a balance. Rust's type system is ultimately fairly simple and limited, but the "unsafe" escape hatch allows us to build all manner of safe abstractions.

**Too little ("almost safe" APIs):** APIs that are safe so long as you don't do "unreasonable" things, such as an API that would be unsafe if a cycle between ref-counting objects was created. Plenty of people do unreasonable things in code, either because they don't yet know what is reasonable or not, or because the complexity of the system gets away from them. The role of the compiler is to manage that for you.

**Too much (static bounds checking):** Requiring the user to statically prove for every `vec[i]`  expression that `i` is in bounds; or to show that `map[key]` is in bounds. This requires another level of "smarts" from the compiler and complexity from the type system. *However,* this form of safety is definitely appropriate for some users and some domains, and we may wish to extend Rust with tooling that allows you to "opt-in", but offering it by default would be "too much".

In general, moving safety checks to runtime can be a useful way to strike a balance between safety and complexity.

### Exhausting matching

Rust code requires exhaustive matching, with explicit `_` cases used to handle additional items. This is different from many languages, such as Scala or Ocaml, which make it a runtime panic to elide cases. This encorages programmers to consider all the cases, or to be explicit when they consider a case impossible, or when they are choosing not to handle a case for the time being.

### Cargo's dependency system

Cargo's dependency system is geared towards reproducible builds. Once an application builds, the `Cargo.lock` file ensures that you don't get surprised by new versions of dependencies that you didn't request.

### Explicit error handling with `?`

Rust eschews exceptions in their traditional form, instead 

