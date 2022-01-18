# How javascript works ?

## Javascript Engine

* Javascript integrated in browsers (like google chrome), the Javascript Engine. It is composed of two things :
  * The `memory heap` (Allocate memory).
  * The `call stack` (read and execute code).

![Engine](docs/simple-engine.JPG#center)

### Memory Heap

* Allocate memory. Example : `const name = 'Antonin'`.
* When there are too many global variables to save large objects, we can talk about `Memory Leak` (overflowing) and if some are not used.

### Call Stack

* Execution of an instruction (1 by 1). Example : `console.log('toto')`.
* It works like a `stack` data structure.

*My code :*

```
	console.log(1);
	console.log(2);
	console.log(3);
```

*In call stack* (1 by 1 execution on the call stack, synchrone execution) :

|--------------|
|console.log(1)| first execution
|console.log(2)| second execution
|console.log(3)| last execution
|--------------|

* Javascript is a single-thread language, it works with only one `call stack`.