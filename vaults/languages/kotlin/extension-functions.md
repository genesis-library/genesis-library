```
StringExtensions.kt

fun String.lastChar() = get(length - 1)
val c: Char = "abc".lastChar()

// in java
import static StringExtensionsKt.lastChar
char c = lastChar("abc");
```

- Kotlin has extensions on collections
list.max() filter() count() flatMap() groupBy() reduce() map() ...