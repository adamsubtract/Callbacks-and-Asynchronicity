## What is the difference between readdirSync and readdir?

readdirSync reads a directory and does not continue until it is done, readdir

reads a directory asynchronously and allows other processes to go on.

## What is the event loop and how does it handle asynchronous requests?

The event loop is what allows Node.js to perform non-blocking I/O operations — despite the fact that JavaScript is single-threaded — by offloading operations to the system kernel whenever possible

## Given the following code, specify whether the program is asynchronous and non-blocking or synchronous and blocking or synchronous and non-blocking.
```
const fs = require('fs');
const file = fs.readFileSync('foo.txt');
console.log(file.toString());
```

synchronous non-blocking

## Given the following code, specify whether the program is asynchronous and non-blocking or synchronous and blocking or synchronous and non-blocking.
```
const fs = require('fs');
fs.readFile('foo.txt', (err, file) => {
 if (err) throw err;
 console.log(file.toString());
});
console.log("test");
```
asynchronous non-blocking

## In what order will the console.log statements execute in the code below?

const fs = require('fs');
fs.readFile('foo.txt', (err, file) => {
 if (err) throw err;
 console.log("A");
 console.log("B")
});
console.log("C");

CAB

## setTimeout is a JavaScript function which calls a function after a set amount of milliseconds. Given the following code, explain in what sequence the functions will run and why.

function greeting() {
 setTimeout(() => {
   console.log("friend");
 }, 100);
}

function hello(){
 console.log("hello");
}

greeting();
hello();

hello
friend

## Create a function which utilizes a callback. Make sure to add console.log statements to understand when your callback function is called.

```
function doHomework(subject, callback) {
  console.log(`Starting my ${subject} homework.`);
  callback();
}

function alertFinished(){
  console.log('Finished my homework');
}

doHomework('math', alertFinished);
```
