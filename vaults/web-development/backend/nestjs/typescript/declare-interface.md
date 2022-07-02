If the file has a `.d.ts` extension, all of the classes are treated as if they were preceded by a `declare` keyword. Declarations don't need an implementation, they just supply type information.


```javascript
// runtime error
declare class Foo {  public bar(): void; }
class FooDerived extends Foo { }
```

```javascript
interface Foo { bar(): void; }
class FooImpl implements Foo { public bar() {} }
```

