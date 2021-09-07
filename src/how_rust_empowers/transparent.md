# 🔧 Transparent: "predict and control low-level details"

> The translation from Rust to underlying machine code is straightforward and predictable. If needed, you have options to control the low-level details of how your application works.

## In tension with

Feeling transparent can be in tension with [supportive] or [productive], because transparency often requires exposing details.

[supportive]: ./supportive.md
[productive]: ./productive.md

## Mechanisms

What are some of the ways that we make Rust feel **transparent**?

### No global costs

Rust strives to avoid features that impose global costs (that is, impose a runtime cost even on projects that don't use them). This is a key part of Stroustroup's definition of [zero-cost abstractions](./transparent.md#zero-cost-abstractions), "What you don't use, you don't pay for". This is the mechanism that encourages us to use ownership instead of a garbage collector, for example, since a garbage collector 