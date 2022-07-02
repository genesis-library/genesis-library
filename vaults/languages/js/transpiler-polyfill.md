ow to make our modern code work on older engines that don’t understand recent features yet?

There are two tools for that:

1.  Transpilers.
2.  Polyfills

```
// before running the transpiler 
height = height ?? 100; 

// after running the transpiler 
height = (height !== undefined && height !== null) ? height : 100;
```


Usually, a developer runs the transpiler on their own computer, and then deploys the transpiled code to the server.

Speaking of names, [Babel](https://babeljs.io/) is one of the most prominent transpilers out there.

Modern project build systems, such as [webpack](https://webpack.js.org/), provide a means to run a transpiler automatically on every code change, so it’s very easy to integrate into the development process.


Polyfills are for missing functions

```
if (!Math.trunc) { // if no such function 
	// implement it 
	Math.trunc = function(number) { 
		// Math.ceil and Math.floor exist even in ancient JavaScript engines 
		// they are covered later in the tutorial 
		return number < 0 ? Math.ceil(number) : Math.floor(number); 
	}; 
}
```



