how is node different than js
Javascript is a programming language 
js engine like chrome's V8 converts js instructions to binary language.
Ryan Dole took advantage of making V8 opoen source and created the node runtime around V8 js engine.
in node We have the followings:
global, process, module, __filename, require
in browser(that uses v8 engine or anything else) has the following:
window, document, history, location, navigator
How does the compiler of javacript work when we pass non browser code:
when V8 sees some code that uses features like reading/writing files, FTP requests , it'll say, OK, I need some help to execute this, and it'll call the corresponding functionality in our Node.js APIs.
Some of the Node.js APIs are written using js and some is written using C or C++.
Here come in the Node.js bindings. These bindings are what lets your JavaScript code call functionality that's implemented in C and C++, which have things like really highly optimized and tested code to encrypt your data or to make calls to your file system, reading and writing files, regardless of which operating system you're on.
So for much of their functionality, the Note APIs will call into these C++ Node.js bindings. 

Where is the actual implementation of Node functionllity lives:
in Libuv. libuv and V8 are the two most important internal components of Node.js.
That's because libuv deals with input and output tasks.
It's this highly optimized library of code written in the C programming language that deals with input output tasks.

When we make an http request wehter we are in mac, windows or any os the js v8 engine will go through the node.js bindings to libuv which can handle the task depends on the os, the js will come later and check the status of the requests, that's why js is an async programming language
"Our JavaScript doesn't have to wait around for the response.
No, just says, OK, operating system.
Let me know when my task is complete and I'll get right back on it as soon as I can."