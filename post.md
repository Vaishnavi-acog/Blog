---
layout: layouts/index.njk
title: Blog Post
---
<link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
		integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T"
		crossorigin="anonymous">

<section class="m-3">JavaScript is everywhere now-a-days. It is used to develop Websites, Server Applications, Games, Smartwatches, Mobile Applications.

It is a scripting and programming language used on the client side to design/develop web pages. 
This language supports OOP's, functional and dynamic programming. Previously, this is used for building client side applications. After the introduction of Node.js, JavaScript is used on server side applications as well. 

## EcmaScripts
### ES5 
This is a ECMA Script version 5 released in 2009. This focus on how the objects are instantiated. In this version, we have to write function keyword and return like normal JavaScript language.

### ES6
This is a ECMA Script version 6 released in 2015. This focus on 
* Template Literals
* Arrow functions
* Promises
* new numbers
* Const/Let
* Typed array
* Array destructuring
* Map/Set
* Symbols 

For more details: [ES6](http://es6-features.org)

#### About Callbacks:

We can also pass functions as parameters to other functions and call them. Callbacks are used to run after the task is completed, which mean it is used as asynchronous programming. Let us write a code to understand.

Basic function program
> function sample(arg1){\
      return arg1\
  }

sample("Hello")

Now let's use callback function
> function sampleCallback(arg1, callback){\
      return arg1\
      callback()\
> }

sampleCallback("Hello Callback", sample)

Here this sampleCallback function will take another function(sample function) as an argument and run inside. This is valid in JS. A function is passed into another function as an argument can be called as Callbacks.

Also, JS works in sequential order (top-down approach). However, in some scenarios the code need to run (or must run) after another task and not in top-down approch. This is called Asynchronous programming. This Callbacks will make sure to run it after all the tasks are completed.

#### Learning about promises:

Did you remember the promises you make? Well, javaScript will.. Eventually, promises work the same way as they work in real life. So whenever the JS will use promise, either it will complete it on time (resolve) or it will forget (reject). 

This will have three stages: 
* Pending
* Resolved
* Rejected

Whenever the promise is resolved, it will console log(resolve) or if it fails to do, it will console log(reject). 

So how promises make a difference, we can use callbacks right? Well, if we want to use multiple callbacks in one function it will be a huge mess and look like a hell. We can call it callback hell :p

Callback hell
> callbackReq1(function(callback1) { \
    callbackReq2(callback1, function(callback2) {  
        callbackReq3(callback2, function(callback3) {    
            console.log(callback3);   
        }, failureCallback);  \
    }, failureCallback);\
}, failureCallback);


Well, to get out the hell and move on with our code, we use promises. Let's make our job a little easier. 

>callbackReq1()\.then(function(callback1) {\
    return callbackReq2(callback1);\
    })\
    .then(function(callback2) { 
    return callbackReq3(callback2);
    })
    .then(function(callback3){console.log(callback3);
}).catch(failureCallback)

Let's write a simple promise function.

>const promise = new Promise(reject, resolve)=>{\
    let condition = true;\
    if(!condition){\
        return reject\
    }\
    else{\
        return resolve\
    }\
}\
promise.then((result)=> console.log(result)).catch((err)=> console.log(err))


Then method is used for resolving the promises, while catch is used for rejecting them. This is super fast in resolving.

#### Async/Await 
This has a sort of promise-based, asynchronous behaviour.
>async function asyncCall() {\
  await console.log('calling');\
}

The keyword await makes JavaScript wait until that promise settles and returns its result.

### ES7
This is a ECMA Script version 7 released in 2016. This is a small update focus on exponentiation operator ** - (2**4)

### ES8
This is a ECMA Script version 8 released in 2017. Available features in this version are 
* Object.entries / Object.values 
* String padding padStart // padEnd
* Trailing comma in functions
* Async/ Await functions

### ES9
This is a ECMA Script version 9 released in 2018. Available features in this version are 
* Asynchronous iterators
* Promise.finally
* Object destructuring

### ES10 
This is a ECMA Script version 10 released in 2019. Available features in this version are 
* Array.flat
* Array.flatMap
* Object.fromEntries
* String.trimStart() & String.trimEnd()
* Optional Catch binding: 
* Function.toString 
* Symbol Description
* BigInt 
* Array.sort

# References
* [JavaScript Info](https://javascript.info/)
* [CallBacks, Promises, Async/Await](https://www.youtube.com/watch?v=PoRJizFvM7s&t=524s)
* [Practice more here](https://exercism.org/ )
* [MDN Asynchronous JS](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous)
* [EcmaScript Versions](https://medium.com/engineered-publicis-sapient/javascript-es6-es7-es10-where-are-we-8ac044dfd964)
  </section>
 