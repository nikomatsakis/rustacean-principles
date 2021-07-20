# ✨ Bring joy to the user

> Our top goal is for Rust users to be productive and empowered. We want people to love using Rust and, if they so choose, to love participating in its community.

This covers both the design of Rust itself but also the way that you interact with users. Keep in mind that the more prominent you are within the Rust community, the more that you represent Rust wherever you go, even if it's on twitter or other places that are arguably a mix of public and private space. Some important aspects of this:

* We are all beginners at something. We always keep the needs of new users in mind and try to avoid "".

At the same time:

* Rust has a lot of users with a lot of needs. Sometimes those needs are in conflict, or they seem to be, and so we have to avoid going too far in one direction.
* You have our own needs and limits too. Just because somebody has a problem doesn't mean *you* have to fix it. Often the right response is a polite no (or just no response at all).

## Examples

### Designing a tool


### Improving Rust's compiler messages

Somebody tweets about a terrible error message. It has a type that is 16K long and is completely opaque. "What a stupid language", they say.

**Just right:** You reply, "Oh, yeah, that message is terrible. Is the code that caused it something I can see?" You can tell they're frustrated, and that's why they're saying how stupid Rust is. Looking at the code, you realize both (a) how to fix their problem and (b) that a quick patch to the compiler would fix it. You do both. They're happy.

**Too much:** As above, but you put aside the work you've been doing and embark on a refactoring odyssey that slows down compilation time by 22% but also does improve this particular error message.

**Too little:** You reply, telling them that they just don't appreciate what Rust is doing for them.

*Note:* I suppose the right response really depends on what you're focused on! In truth, there's no harm in shrugging and moving on here, or just helping them to fix their code, if fixing error messages is not your thing. There's also no harm in doing a lot of work to address this error, if it's a common case and it's your thing. Slowing down the compiler by 22%, though, that's probably not so great (it will not bring joy to users). But no matter what you do, there's no sense in getting angry at them because they think Rust is stupid. The compiler *is* pretty stupid a lot of the time (like every computer program...).

### Responding on an issue

Someone opens an issue claiming a bug in Rust. In fact, the problem is that their code was relying on an implementation detail of a method in the standard library -- this is despite the fact that the documentation for the function clearly states that this detail may change.

**Just right:** You thank them for higlighting this change, and point out that the problem is actually not a bug in Rust, but rather a change that is within the documentation.

**Too much:** You apologize profusely and revert the PR that made the change. You wind up in a long conversation with the 

**Too little:** You reply curtly, "Not a bug, RTFM", and close the issue.