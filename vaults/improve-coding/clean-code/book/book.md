If a name requires a comment, then the name does not reveal its intent.
Do not refer to a grouping of accounts as an `accountList` unless it’s actually a `List`

Disinformative, noninformative

Noise: ProductData, ProductInfo: data and info is noise words like a, an, the
NameString -> Name, CustomerObject vs Customer? `distinguishable` 

Pronounceable Names: Programming is a social activity
Longer names are more searchable.

Older days, ppl were using hungarian notation, now it is unnecessary.

IShapeFactory vs ShapeFactory
I don’t want my users knowing that I’m handing them an interface. I just want them to know that it’s a `ShapeFactory`
So if I must encode either the interface or the implementation, I choose the implementation. Calling it `ShapeFactoryImp`

In general programmers are pretty smart people. Smart people sometimes like to show off their smarts by demonstrating their mental juggling abilities
One difference between a smart programmer and a professional programmer is that the professional understands that _clarity is king_.


Classes and objects should have noun or noun phrase

Methods should have verb or verb phrase like `postPayment`
`get`, `set`, and `is`


When constructors are overloaded, use static factory methods:
```
Complex fulcrumPoint = Complex.FromRealNumber(23.0);
Complex fulcrumPoint = new Complex(23.0);
```

Say what you mean. Mean what you say.

### **Pick One Word per Concept**
insert or add?
controller, manager, driver?


The name `AccountVisitor` means a great deal to a programmer who is familiar with the VISITOR pattern.




Functions ====
Must be small
he blocks within `if` statements, `else` statements, `while` statements, and so on should be one line long. This should be a function.

functions should not be large enough to hold nested structures. Therefore, the indent level of a function should not be greater than one or two.

**_FUNCTIONS SHOULD DO ONE THING. THEY SHOULD DO IT WELL. THEY SHOULD DO IT ONLY._**

if a function does only those steps that are one level below the stated name of the function, then the function is doing one thing.
if you can extract another function from it with a name that is not merely a restatement of its implementation, then its not doing one thing
In order to make sure our functions are doing “one thing,” we need to make sure that the statements within our function are all at the same level of abstraction.
high level: getHtml()
mid level: PathParser.render(pagePath)
low level: .append()

reader may not be able to tell whether a particular expression is an essential concept or a detail.

Making the code read like a top-down set of _TO_ paragraphs is an effective technique for keeping the abstraction level consistent.


