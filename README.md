# rustlang-notes

## History and Current Status
Originally started at Mozilla as a research project by Graydon Hoare.
Notable project that is written in Rust include `Servo`, the layout engine of Firefox.

## Paradigm
Imperative, functional, generic

## Typing System
Strong, static

## Control Strucutres
Similar to other imperative lanaguges (C/C++/Java), has if/else, while, for constructs for condition and loop.
In addition, Rust has a `loop` construct for inifinite loop.
Also has `match` construct for pattern matching similar to that of some functional languages (e.g. Haskell).

## Semantics

### Scope
Static scoping, scope is determined at compile time.

### Ownership
Rust has the concept of ownership to help manage memory allocation.
In essense, value (and the memory it occupy) can only lives as long as its owner.
When the owner reaches the end of its lifetime, the value will be released appriorately according to how it is allocated (stack or heap).

The transfer of ownership is similar to the move semantics in C++, where the value is given to the new owner, and the old "name" is no longer valid.

> - Each value in Rust has a variable that’s called its owner.
> - There can only be one owner at a time.
> - When the owner goes out of scope, the value will be dropped.
>
> from [The Rust Programming Lanaguage](https://doc.rust-lang.org/book/ch04-01-what-is-ownership.html#ownership-rules)

### Error Handling
Rust does not have exceptions, all recoverable errors are propagate in the form of values (e.g. Result<T, E>), similar to that of functional languages like Haskell.

Because Rust has pattern matching for enum types, which makes error handling easier, but this can also leads to deeply nested construct for error handling, in which case, code needs to be factor out into functions for better readbility.
e.g.
```rust
let x = match field.parse::<f32>() {
    Ok(val) => val,
    Err(e) => {
        eprintln!("{}", e);
        return None;
    }
};
```

### Lifetime Annotation
Rust has lifetime annotation for situtaions where Rust compiler is unable to reason about the lifetime of references.

## Desirable Language Characteristics

- Rust does not have a runtime system, which means there is no additional runtime burden, thus can have better efficiency than languages that has a runtime.
- In Rust, you can embed assembly code, which means Rust is capable of being used in bare metal environment (e.g. embedded device, bootloader, Operating System).
- The concept of ownership and lifetime allows Rust to manage the memory automatically, and by in large eliminiated most memory bugs, thus better security & relaibility.

