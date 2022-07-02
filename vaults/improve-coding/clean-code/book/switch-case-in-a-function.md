![[Pasted image 20220615120548.png]]

Problems
- Large, when new types added it will grow
- Does more than one thing
- SRP violation, more than one reason to change it: like what?
- OCP violation: it must change whenever new types are added.


Bury this switch statement into basement of an Abstract Factory.

“_You know you are working on clean code when each routine turns out to be pretty much what you expected._”

Testing a function is hard, when it has more than 2 arguments.

Flag arguments
It means function does 2 things!


Even obvious dyadic functions like `assertEquals(expected, actual)` are problematic. How many times have you put the `actual` where the `expected` should be? The two arguments have no natural ordering. The `expected,` `actual` ordering is a convention that requires practice to learn.

`outputStream.writeField(name)` instead of `writeField(out, name)`

`assertEquals` might be better written as `assertExpectedEqualsActual(expected,` `actual)`. This strongly mitigates the problem of having to remember the ordering of the arguments.


Anything that forces you to check the function signature is equivalent to a double-take. It’s a cognitive break and should be avoided.


Should not have side effects
CQRS

### **Prefer Exceptions to Returning Error Codes**

It promotes commands being used as expressions in the predicates of `if` statements.  
if (deletePage(page) == E_OK)
leads to deeply nested structures.

use try/catch instead and extract them.

Functions should do one thing. Error handling is one thing.
Thus, a function that handles errors should do nothing else.




Master programmers think of systems as stories to be told rather than programs to be written.