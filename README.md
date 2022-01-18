# How javascript works ?

## Javascript Engine

* Javascript integrated in browsers (like google chrome), the Javascript Engine. It is composed of two things :
  * The `memory heap` (Allocate memory).
  * The `call stack` (read and execute code).

![Engine](docs/simple-engine.JPG#center)

## Memory Heap

* Allocate memory. Example : `const name = 'Antonin'`.
* When there are too many global variables to save large objects, we can talk about `Memory Leak` (overflowing) and if some are not used.

## Call Stack

* Execution of an operation (1 by 1). Example : `console.log('toto')`.
* It works like a `stack` data structure.

*My code :*

```
	console.log(1);
	console.log(2);
	console.log(3);
```

*In call stack* (1 by 1 execution on the call stack, synchrone execution) :

```
|--------------|
|console.log(1)| first execution
|console.log(2)| second execution
|console.log(3)| last execution
|--------------|
```

* Javascript is a `single-thread` language, it works with only one `call stack`. It's different from `multi-thread`.
* When there are too many operations to execute, it's `stack overflow`.

## Single-thread non-blocking ?

* The synchronous is blocking (we have to wait until the previous task is finished).
* It is necessary to use asynchronous to have single-thread non-blocking (Run-Time Environment on Javascript).

### Loop system

![Engine](docs/engine.JPG#center)

* 1- Check if there are operations in the `call stack`.
* 2- If empty, check if there are operations in the `callback queue` (It works like a `queue` data structure).
* 3- If there is an operation, it is transferred to `call stack` and executed.

### Example

*Code* :

```
console.log('start') // In call stack
element.addEventListener('click', event => event.target.remove()) // In 'callback queue' and transferred in 'stack call' if element are clicked
console.log('end') // In call stack
```

## Summary

* Javascript is an single-thread language and can be non-blocking with Asynchronous operations.