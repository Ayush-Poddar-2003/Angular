# Basics
In Js, there are 2 kinds of operations:

### 1. Synchronous
Synchronous = wait until task finishes, then move ahead

```js
console.log("Task 1");
console.log("Task 2");
console.log("Task 3");

// Everything runs one by one in order
```

---
### 2. Asynchronous (takes time)
Asynchronous = don’t wait, continue other work

```js
console.log("Start");

setTimeout(() => {
  console.log("Tea is ready");
}, 2000);

console.log("End");
```
    // Output
    Start
    End
    Tea is ready

> JavaScript executes synchronous code first, then async code later

---

How JavaScript Executes Code ?
1. Runs code top to bottom
2. If async found → send to browser, Task is scheduled, Will run after condition (time/API/etc)
3. Continue next lines
4. All async tasks start when JS reaches them, They DO NOT wait for each other, They run independently, Output depends on completion time

---
# <center> CALLBACKS
Callbacks are the foundation of async programming in JavaScript.  
Everything evolved like this:
Callback → Promise → RxJS

> A callback is a function that is passed into another function and executed later.

```js
function main(callback) {
  console.log("Main function running");

  callback(); // main decides when to run it
}

function sayHi() {
  console.log("Hi");
}

main(sayHi);
// Output
// Main function running
// Hi
```

main(sayHi); ✅ This IS callback  
main(sayHi( )); ❌ This is NOT callback: runs immediately

```js
function process(callback) {
  console.log("Processing...");
  callback();
}

//func called and callback passed
process(() => {
  console.log("Done!");
});
```

---

# <center> PROMISES
A Promise is an object that represents a value that will be available in the future.  
Promise always represents future result

A Promise:  
Handles one async value,  
Executes immediately,   
Cannot be cancelled once started

---
### <CENTER>RESOLVE -
Syntax:-
```js
new Promise((resolve, reject) => {
  resolve(value);
});
```

`new Promise((resolve, reject)`  
You are creating a promise -    
resolve = success function  
reject = failure function

`resolve(value)`  
Task finished successfully, here is value, It goes to .then()

```js
const p = new Promise((resolve) => {
  resolve("Done");
});

p.then((data) => {
  console.log(data);
});
```

`.then((data) => { ... })`  
Receives that value