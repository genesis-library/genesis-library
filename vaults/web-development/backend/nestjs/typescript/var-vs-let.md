```typescript
// this works because of hoisting, which is confusing.
console.log(myVar)
var myVar = "aaaa"
```

ts infers types
```typescript
let x: string = "str";
x = 42 // gives error

// is same with

let x = "str";
x = 42 // gives error.
```

union

```typescript
let x : string | number
x = 42 
x = "aaa"
```

strictNullChecks 
```typescript
let str : string;
str = null; // error

let str : string | null | undefined;
str = null // ok
```

type assertion
```
let value : any = 5;
(<number>value).toFixed(4); // 5.000
(value as number).toFixed(4); // 5.000
```

```
asfgdgfa
```

control flow based type 

-- noImplicitAny
--strictNullChecks