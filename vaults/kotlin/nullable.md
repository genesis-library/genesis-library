- Make Null Pointer Exception compile time error, not runtime error.

```
val s1: String = null X
val s2: String? = "can be null or non-null"

s1.length OK
s2.length CAN BE WRONG?
```