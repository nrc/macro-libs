# Context

We currently pass MacroContext in TLS

Question: should we keep it in TLS or pass to proc macros as a param (#1)

Would be good to be able to initialise MacroContext in TLS outside of the compiler
* i.e., make the proc macro system available outside of proc macros 
* e.g., in a build script, bindgen
* creating a token stream requires TLS state

