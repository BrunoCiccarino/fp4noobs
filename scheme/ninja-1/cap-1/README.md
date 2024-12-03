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