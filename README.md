Idris Elba
==========

Idris Elba is an experimental whitespace-based functional programming language with dependent types.

Background
----------

[Edwin Brady](http://edwinb.wordpress.com/) is the creator (with others) of the Idris and Whitespace programming
languages. Idris Elba is a synthesis of the primary ideas in both languages, nameley dependent typing and using
whitespace for everything.

The suffix "Elba" is inspired by the surname of the British actor [Idris Elba](http://www.imdb.com/name/nm0252961/),
and means "white".

Examples
--------

The syntax of Idris Elba is very close to that of Whitespace. An Idris Elba "hello world" program might look like this:

                                                               

Idris Elba features dependent types. Here is a quicksort example showing featuring a return type of sorted list:



                                                                
                                                                                                                                
                                                                                                                                                                                                

Dependent types can also be used to express constraints on the arguments to functions. Here is an example showing that
a function taking the head of a list is only defined for non-empty lists:



                                                                
                                                                                                                                                                                            
                                                                                                                                                                                            

Building
--------

To configure, edit config.mk. The default values should work for most people.

To install, type 'make'. This will install everything using cabal and
typecheck the libraries.

To run the tests, type 'make test' which will execute the test suite, and
'make relib', which will typecheck and recompile the standard library.

Idris Elba has optional buildtime dependencies on the C libraries llvm-3.3 and libffi. If you would like to use the features that these enable, be sure these are compiled for the same architecture as your Haskell compiler (e.g. 64 bit libraries for 64 bit ghc). By default, Idris builds without them. To build with them, pass the flags -f LLVM and -f FFI, respectively.

To build with LLVM and libffi by default, create custom.mk or add the following line to it:
CABALFLAGS += -f LLVM -f FFI
The file custom.mk-alldeps is a suitable example.

Idris has a runtime dependency on libgmp, and on Boehm GC (libgc) when using the LLVM codegen. These are needed for linking into compiled programs, so be sure these are compiled for Idris's default target architecture (usually 64 bit on x86_64 systems).

The Idris wiki contains instructions for building on various platforms and for getting involved with development. It is located at https://github.com/idris-lang/Idris-dev/wiki .
