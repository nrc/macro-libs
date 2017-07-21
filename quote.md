# quasi-quoting

## Current status

Currently supported by `quote!` in the compiler.

https://github.com/dtolnay/quote is similar

The old built-in macros like `quote_stmt!` produce AST rather than tokens.


## Notes

Syn not using quote!

`quote_span!` is desirable - quote text and assign a span (though we need some user-friendly representation of spans)

