- overriding methods
```
override fun foo()
```

- **Unit** Returning
like void in java
you can omit it in function definition.
- default arguments
```
fun read(
	b: ByteArray,
	off: Int = 0
){...}


// default parameter values must be omitted 
// if the overrided method has default parameter.
open class A{
	open fun foo(i: Int = 10){}
}

class B: A(){
	override fun foo(i: Int){} // default is not allowed here.
}

```

- named arguments
```
fun foo(
	bar: Int = 0
	baz: Int
)

foo(bar = 1, baz = 1)
foo(baz = 1) // you can skip parameters with default arguments.
foo(baz = 1) equals to foo(0, 1)
```
- lambda naming arguments (if lambda function is the last argument)
```
fun foo( bar: Int = 0, baz: Int = 1, qux: () -> Unit, ) { /*...*/ } 
foo(1) { println("hello") }
foo(qux = { println("hello") })
```

- vararg
```
fun foo(vararg string: String)
foo(strings = *arrayOf("a", "b", "c"))
foo("a", "b", "c")
```

- some functions
asList, toList, asArray, toArray, intArrayOf, arrayOf, toTypedArray...