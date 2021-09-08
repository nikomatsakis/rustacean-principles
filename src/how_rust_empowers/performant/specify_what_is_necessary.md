# Specify only what's necessary

> Specify the details that are needed to capture the programmer's intent, but not more.

Many details of Rust are left deliberately unspecified. For example, unless users manually add a `repr` attribute, Rust structs and enums can be laid out in memory however the compiler sees fit. This allows us make optimizations like reordering struct fields to eliminate padding and reduce size, or representing `Option<&T>` as a single, nullable pointer. (Of course, reserving this freedom works against [transparency] and [versatility], which is why we have the option to specify the `repr`.)
