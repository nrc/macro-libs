# TokenStreams

The primary token structure in the compiler/proc macro interface

## Issues

Translate ast to token stream loses spans
* compiler implementation issue - why are we providing an AST at all, rather than a token stream?
* fixed by acrichto PR?

Literal support
* pull the value out of a value
* doc strings
* constructing a literal

Improve the iterator. Perhaps make (or expose) a cursor - jump in/out/back of trees.

