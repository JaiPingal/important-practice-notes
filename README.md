### Important Practice Notes with interview questions

### Table of Contents

<!-- 1. [ReactJs](#reactjs) -->
1. [Javascript Codding Questions](https://github.com/Vasu7389/JavaScript-Interview-Questions?tab=readme-ov-file#23-write-a-function-in-javascript-that-removes-duplicates-from-an-array)
2. [Javascript Advance Questions](https://github.com/lydiahallie/javascript-questions/)
3. [ReactJs Questions](https://github.com/Learn-with-Sumit/reactjs-interview-questions-1?tab=readme-ov-file/)
4. [React Native Interview Questions](https://github.com/samsoul16/react-native-interview-questions)

<!-- ### ReactJs
ReactJs is a popular JavaScript library for building user interfaces. It is maintained by Facebook, and is widely used for building web applications, mobile apps, and other user interfaces. React allows developers to create reusable components, which can help make large applications easier to manage and maintain. It is designed to be efficient, declarative, and flexible, and can be used to create complex, dynamic user interfaces. -->

- - - -

#### How to javascript work ?

Whenever we run the JS code our browser th browser has a Js engine, every JS engine has a parser, in which parser our JS code checks it line by line is the syntax wise correct or note? Because Javascript is an interpreted language. And this is where an error occurs in its code, and parser stops executing its.
When the parser produce the ATS(Abstract Syntax Tree).\
The Js code is translated into machine code with the he lp of ATS and when it gets converted into machine code only then the actual code runs.

#### Execution Context

Execution context is the environment in which our code is executed and is evaluated. \
Whenever we write code an environment is required to run that Js code. The environment where we run and evaluate our code is called execution context. \
There is also an execution context inside the execution context which we call global execution context. This is by default.

By default means:-
*Js engine created the global execution context before the start to execute any code.*

***Variable and function that not inside any function. A new execution context get create every time a function is executed***

**Note:-**
Until we call the function, it remains in the global execution context, but as soon as we call the function and it is executed, each function get a new execution context.

#### Execution stack 

Execution stack also know as "calling stack" is a stack with a LIFO structure, which is used to store all the execution context during the code execution. \

Execution context has two phase.

**(I) Creation phase**

in this creation phase three properties 

***(i) Variable object*** \
***(ii)Scope chain*** \
***(iii)this variable***

**(II) Execution phase**

#### Variable object:-

(1) for each function (function declaration) a property is created in  the variable object, which pointing to that function\

***Means:-*** \
First of all in  the creation phase it is checked where the function is being declaration and where the functions is being declared; a property is created inside the variable object and it is pointed.

(2) For each variable (Variable declaration) a property is created in the variable object then set to undefined.

**Note:-**
This line 1 or line 2 is called Hosting in Javascript 

***Hosting***

Hosting is a Javascript mechanism where variable and function declaration are move top of there scope before code execution. \
In Javascript, where code is created in the creation phase, all the variables the top of there scope before the code is executed

**Note:-**
Hosting works only on function declaration or var keyword not in function execution and fat Arrow function and let & const

##### Scop Chain

The scop chain is used to resolved the value of variable name in Javascript. \
If we are writing code in javascript than scop chain helps us in determining which variable should have which value. \

Scop chain in javascript is lexically defined which means that we can see what the scop chain will be by looking at the code.

At the top of hte scop chain is the global scop, which is the window object in the browser.

***Lexically scoping:-*** \
A function that is lexically within another function get access to the scop or the outer function. \
***(inner function can get to access to there parent function variable but the vice-versa is not true.)***

#### this keyword

'this' keyword refers to an object that is executing the current piece of code, it references the object is executing the current function being referenced is a 'regular function' "this" references the global object. If the function that is being referenced is a method in an object "this" references the object itself.

#### Event loop in Javascript

Javascript event loop is the core mechanism that enables asynchronous operations. \
Though single-threaded, it manages task efficiency.

Imagine it as a queue system events like user interactions or networks requests are added to the queue, and the engine processes then one by one.

This allows javascript to handle non-blocking tasks without freezing keeping the application responsive event white waiting for data or other operations.

***Javascript is a Synchronous Single-threaded language. Means: Javascript code is runs in one line at a time***

#### Micro-tasks and Macro-tasks in event loop.

Javascript has a concurrency model based on an event loop, which is responsible for executing events and executing queued Sun-tasks.

**Concurrency Model Meaning:-** \
In concurrency modeling, object for a board are allocated to tasks that appear to run simultaneously.

Within the Event Loop there are are actually 2 types of queues:

***(i)macro tasks queue(or just collect the task queue)*** \
***(ii)micro tasks queue***

#### Macro-task:

A macro task queue is a short function which is executed after the function or program which created it exits and only if the javascript execution task is empty. \
***Promise callback*** \
***queue Micro tasks***

#### Macro-task:

A macro tasks is short function which is executed after javascript execution stack and micro tasks are empty
***SetTimeout*** \
***SetInterval*** \
***SetIntermediate*** 

#### Callback function()

Any function that is passed as an argument is called callback function.\
* A callback is a function that to be executed after another function has finished executing - hance the name callback function. \
**OR**
* Callback functions are functions that are called after the first function completes its task. They are often used to handle asynchronous events and make your code more readable. 
**Why callback function?**

Callback functions are important in JavaScript because they let you create asynchronous code that doesn’t block the main thread of execution. This enables you to perform other tasks, such as user interface (UI) updates or other API calls, while an asynchronous action is executing.

**When to Use a Callback Function?**

* When making an asynchronous API call.
* When listening for events.
* When running a long-running task.
* When working with promises.

**Synchronous vs Asynchronous Callback Functions**

***Synchronous callback functions execute instantly, but asynchronous callback functions execute at a later time.***

* Synchronous Callback:-

```js
function greet(name, callback) {
    console.log(`Hello ${name}`);
    callback()
};

function sayGoodbye() {
    console.log("Goodby!")
};
greet("Jai", sayGoodbye)
```

* Asynchronous callback:-

```js
function asyncOperation(callback) {
    console.log("Start of Operation");
    setTimeout(function() {
        callback();
    }, 1000);
    console.log("End of Operation");
};

function callback() {
    console.log("Callback executed")
};
asyncOperation(callback)
```

#### Closures

A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives a function access to its outer scope. In JavaScript, closures are created every time a function is created, at function creation time.

```js
function init() {
    var name = "Mozilla"; // name is a local variable created by init
    function displayName() {
        // displayName() is the inner function, that forms a closure
        console.log(name); // use variable declared in the parent function
    }
    displayName();
}

init();
```

```js
const makeCounter = function() {
    let privateCounter = 0;

    function changeBy(val) {
        privateCounter += val;
    }
    return {
        increment() {
            changeBy(1);
        },

        decrement() {
            changeBy(-1);
        },

        value() {
            return privateCounter;
        },
    };
};

const counter1 = makeCounter();
const counter2 = makeCounter();

console.log(counter1.value()); // 0.

counter1.increment();
counter1.increment();
console.log(counter1.value()); // 2.

counter1.decrement();
console.log(counter1.value()); // 1.
console.log(counter2.value()); // 0.
```

```js
// global scope
const e = 10;

function sum(a) {
    return function(b) {
        return function(c) {
            // outer functions scope
            return function(d) {
                // local scope
                return a + b + c + d + e;
            };
        };
    };
}

console.log(sum(1)(2)(3)(4)); // 20
```
