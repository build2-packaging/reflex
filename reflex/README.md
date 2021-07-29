# reflex

`reflex` is a variant of `flex`, a tool for generating scanners (programs
which recognize lexical patterns in text).

It reads the given input files for a description of a scanner to generate. The
description is in the form of pairs of regular expressions and C code, called
rules. Reflex generates as output a C source file, `lex.yy.c`, which defines a
routine `yylex()`. When this routine is called, it analyzes its input for
occurrences of the regular expressions. Whenever it finds one, it executes the
corresponding C code.

`reflex` is based on `flex` 2.5.4a, and unlike so-called "new" `flex`, remains
compatible with POSIX `lex`.

Note that for better compatibility with "new" `flex`, this package has applied
a patch to allow specifying `-o`, `-P`, and `-S` option values as separate
arguments, for example:

```
reflex -P yyy -o scan.c scan.l
```
