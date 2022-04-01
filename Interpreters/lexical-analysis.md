# Lexical Analysis

Lexical analysis is the process of converting a sequence of characters into a sequence of tokens.

Can also be referred to as a tokenizer.

## Example


```
let x = 5 + 5;
```

The above can be converted into something like

```
[
    LET,
    IDENTIFIER("x"),
    EQUAL_SIGN,
    INTEGER(5),
    PLUS_SIGN,
    INTEGER(5),
    SEMICOLON
]
```

This is fed into the interpreter to be turned into an abstract syntax tree.