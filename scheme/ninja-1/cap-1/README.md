# Expressions 

In C or Cpp, a call to a foo procedure with arguments bar and baz is written

` c
foo(bar,baz);
`
but in the Scheme it is written

` scheme
(foo bar baz)
`
Note that the name of the procedure goes inside the parentheses, along with the arguments. Get used to it. It may seem less strange if you think of it as an operating system shell command--for example, rm foo, or dir bar---but enclosed in parentheses.

Just like in C, expressions can be nested. Here is a call to a procedure foo, with nested procedure call expressions to calculate the arguments.

` scheme
(foo (bar x) (baz y))
`
This is practically equivalent to C's

` C
foo(bar(x),baz(y));
`

As in C or Cpp, argument expressions in a procedure call are evaluated before actually calling the procedure; the resulting values ​​are what is passed to the procedure. In Scheme terminology, we say that the procedure is applied to the actual argument values.

You will soon notice that Scheme has very few special characters and that expressions are usually delimited by parentheses or spaces. For example, a-variable is a unique identifier, not a subtraction expression. Identifiers in Scheme can include not only alphabetic characters and digits, but various other characters, such as !, ?, -, and _. Long identifiers are often constructed from phrases to make clear what they mean, using hyphens to separate words; for example, you might have a variable called list-of-first-ten-lists. You can use characters such as +, -, *, and / within an identifier, as in before-tax-total+tax, or estimate+epsilon.

### Primitive types

In scheme objects can be considered primitive types. C

- haracters, strings, numbers and booleans are common in most programming languages. 
- Pairs, used to implement lists, are native types in Scheme
- Vectors are native types in Scheme.
- Byte vectors (bit sequences) are native types.
- Procedures are native types.
- Input and output ports are native types.
- The end-of-file object is a single element of a native tip
- The empty list is the only element of its type.
- Symbols (variable names) are native types.

The Scheme standard defines that each object must be of exactly one of these types, and there are procedures that check the types of these objects.

### Variables

In programming, variables are like boxes, which store values, so we can describe what we want, we give names to these boxes. In Scheme, a variable name is a symbol. It is important to note that a symbol is not a variable. He is a name that can be
linked to a variable, and this name can be manipulated as if it were an object like any other. A symbol is also not a string of characters. A Scheme interpreter, when reading a sequence of characters between quotation marks, you will recognize that it is a string:

`(string? "Oh brave new world")` 

But a sequence of characters, without quotes, is not a string. It's a name, or symbol:
`(string? (quote abcde))`
- #f (#f means false)
`(symbol? (quote abcde))`
- #t (#t means true)

It is possible to transform symbols into strings and vice versa, with the **string->symbol** procedures and **symbol->string**.
`(string->symbol "brave")`
- brave
`(symbol->string (quote world))`
- “world”

### Basic syntax

Scheme's syntax is very simple: everything in the language is done with s-expressions. (sexp’s for short.) A simple s-expression is an atom (such as a symbol, number, string) or series of atoms surrounded by parentheses. S-expressions can be nested to any depth we want.