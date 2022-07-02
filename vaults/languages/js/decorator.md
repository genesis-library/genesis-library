https://www.sitepoint.com/javascript-decorators-what-they-are/

functional composition ```doubleIt(doubleIt(doubleIt(2)))```
higher-order functions 

first you need to know about ```object properties```
```
const object1 = {};

Object.defineProperty(object1, 'property1', {
  value: 42,
  writable: false
});

object1.property1 = 77;
// throws an error in strict mode

console.log(object1.property1);
// expected output: 42

```


and ```Function.prototype.apply()```

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply?retiredLocale=tr

babel [transform-decorators-legacy plugin](https://github.com/loganfsmyth/babel-plugin-transform-decorators-legacy).

you cant use functional composition for classes or their properties.