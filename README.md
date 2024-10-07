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

By default means: \

    Js engine created the global execution context before the start to execute any code.

***Variable and function that not inside any function. A new execution context get create every time a function is executed***

**Note**
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

**Note**
This line 1 or line 2 is called Hosting in Javascript 

***Hosting***

Hosting is a Javascript mechanism where variable and function declaration are move top of there scope before code execution. \
In Javascript, where code is created in the creation phase, all the variables the top of there scope before the code is executed

**Note**
Hosting works only on function declaration or var keyword not in function execution and fat Arrow function and let & const
