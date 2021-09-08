# Improving Rust's compiler messages

> Somebody tweets about a terrible error message. It has a type that is 16K long and is completely opaque. "What a stupid language", they say.

**Just right:** You reply, "Oh, yeah, that message is terrible. Is the code that caused it something I can see?" You can tell they're frustrated, and that's why they're saying how stupid Rust is. Looking at the code, you realize both (a) how to fix their problem and (b) that a quick patch to the compiler would fix it. You do both. They're happy.

**Too much:** As above, but you put aside the work you've been doing and embark on a refactoring odyssey that slows down compilation time by 22% but also does improve this particular error message.

**Too little:** You reply, telling them that they just don't appreciate what Rust is doing for them.

*Note:* I suppose the right response really depends on what you're focused on! In truth, there's no harm in shrugging and moving on here, or just helping them to fix their code, if fixing error messages is not your thing. There's also no harm in doing a lot of work to address this error, if it's a common case and it's your thing. Slowing down the compiler by 22%, though, that's probably not so great (it will not bring joy to users). But no matter what you do, there's no sense in getting angry at them because they think Rust is stupid. The compiler *is* pretty stupid a lot of the time (like every computer program...).
