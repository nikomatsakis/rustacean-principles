# Charter

## What is Rust

A language empowering everyone to build reliable and efficient software. 

## What kind of appliations is Rust aiming at?

Rust targets applications where the following are top consideratons:

* **Security and correctness:** Rust's type system not only ensures that programs don't have memory safety bugs or data races, it also encourages a [robust and reliable][reliability] programming style that tends to find and uncover bugs before they happen.
* **Resource usage:** Rust's default idioms are [performant], and Rust's [transparent] nature lets you see and control the performance costs your code will incur.
* **Portability:** The Rust standard library and toolchain work across Windows, Mac, and Linux and across multiple architectures. Rust's API try to be [productive], meaning that it is easy to do the most common things and have them work everywhere you want them to. At the same time, Rust's focus on [versatility] means that we also make it possible to expose the specialized and unique features that your particular operating system offers.

## When might I choose to use another language?

Rust is a great language, but it's not the best for everything. Here are some reasons you might prefer to use a different language:

* if the code you are writing is temporary or single purpose;
* if you prize agility over finding and fixing bugs early;
* if you don't care how much memory, CPU, or power your program uses;
* if you know another language well, and you have to deliver code on a tight timeframe.

That said, one of Rust's goals is [productivity]: many people find that once they are familiar with Rust, it becomes their "go to" language even for applications that are outside its target area, simply because of tools like cargo and the rich set of library available on crates.io.