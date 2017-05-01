# Rust Macro libraries

Planning out APIs for procedural macros.

See [RFC 1566](https://github.com/rust-lang/rfcs/blob/master/text/1566-proc-macros.md)
and this [blog post](http://ncameron.org/blog/libmacro/).

## Goals

The Rust distro should include a very low-level library for creating procedural
macros. External crates should build on top of this low-level API to provide
more high-level APIs for macro authors. Eventually some high-level crates may be
moved to the distro, but they should prove themselves first 'in the wild'.

The Rust distro should also provide a decent `quote` macro for quasi-quoting at
the token level (quasi-quoting at the AST level belongs in external crates). I
expect this to be a universal enough requirement for macros that we should
provide it initially. It is also a nice way to provide some abstraction.

The APIs we provide should be:

* ergonomic for library authors, not necessarily macro authors,
* efficient,
* complete.

Ideally, there should be a separation between this macro library and what the
compiler uses internally, so as not to restrict refactoring of the compiler.
However, for the sake of efficiency and completeness, the two APIs should be
similar where possible. That means we should strive to make our APIs general
enough that they do not restrict the implementation. In particular, we should
avoid any connection with the AST.

### Areas to cover

* Token and TokenStream representation and manipulation
* Creating tokens
* Tokenising (lexing) a string
* Quasi-quoting (`quote!`)
* Pattern matching (`match!`, to give a facility similar to matchers in declarative macros)
* Name resolution/item lookup
* Span manipulation
* Hygiene manipulation
* Generating fresh names (cc gensym)
* Expansion of macros
* Handling interned strings and names
* Parsing helper functions (e.g., to handle key/value arguments in attributes)
* Feature gates
* Attributes (mark as used, perhaps more?)
* Error handling

## Design philosophy

TODO

## Current APIs

TODO

## Examples

* [Darkly](https://github.com/nrc/darkly) A scanln macro.
