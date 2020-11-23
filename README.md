# rustlang-notes

## History and Current Status
Originally started at Mozilla as a research project by Graydon Hoare. Notable project that is written in Rust include `Servo`, the layout engine of Firefox.

## Paradigm
Imperative, functional, generic

## Typing System
Strong, static

## Control Strucutres
Similar to other imperative lanaguges (C/C++/Java), has if/else, while, for constructs for condition and loop. In addition, Rust has a `loop` construct for inifinite loop.

## Semantics
Static scoping, scope is determined at compile time.

### Ownership
Rust has the concept of ownership to help manage memory allocation.
> - Each value in Rust has a variable that’s called its owner.
> - There can only be one owner at a time.
> - When the owner goes out of scope, the value will be dropped.
> from [The Rust Programming Lanaguage] (https://doc.rust-lang.org/book/ch04-01-what-is-ownership.html#ownership-rules)

## Desirable Language Characteristics

- Rust does not have a runtime system, which means there is no additional runtime burden, thus can have better efficiency than languages that has a runtime.
- In Rust, you can embed assembly code, which means Rust is capable of being used in bare metal environment (e.g. embedded device, bootloader, Operating System).
- The concept of ownership and lifetime allows Rust to manage the memory, and by in large eliminiated most memory bugs, thus better security & relaibility.

