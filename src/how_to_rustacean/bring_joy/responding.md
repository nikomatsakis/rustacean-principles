# Responding on an issue


> Someone opens an issue claiming a bug in Rust. In fact, the problem is that their code was relying on an implementation detail of a method in the standard library -- this is despite the fact that the documentation for the function clearly states that this detail may change.

**Just right:** You thank them for higlighting this change, and point out that the problem is actually not a bug in Rust, but rather a change that is within the documentation. If appropriate, you might express sympathy for the impact of this change on them, and you consider if there *may* be a way to better advertise or guard against such impact in the future, but you close the current issue.

**Too much:** You apologize profusely and revert the PR that made the change. You wind up in a long conversation with the 

**Too little:** You reply curtly, "Not a bug, RTFM", and close the issue.
