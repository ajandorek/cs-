# cs-Homework

# JS in more Depth

## Table of Contents

1. Table of Contents
2. Homework Details
3. Core JavaScript Questions
4. ES6 Questions
5. Node.js Questions
6. React.js Questions
7. Internet/Network questions

## Homework Details

This homework is designed to prepare you for questions you may face during an interview. It should take you no more than 4 hours. It's akin to an open book quiz since you can use the internet to look things up. But first, try going through and seeing how many questions you can answer without using google/stackoverflow/anyOtherInternetSource! And then go back and look up the answers to the ones that stumped you.

## Core JavaScript Questions

1. What is the difference between `undefined` and `not defined` in JavaScript?

        •Not defined means the variable does not exist in memory since it isn’t defined in the program. Undefined means that the variable exists but does not have any data. 

2. What is "Hoisting" in JavaScript?

When a function is declared after it is used.

3. What would be the output of the following code?
```javascript
    var y = 1;
      if (function f(){}) {
        y += typeof f;
      }
     console.log(y);
```
    •	yundefined

4. What is a "private method"?

A method that can only be called within the same class or module. 

5. What is the drawback of creating true private methods in JavaScript?

A new method would have to be created for each instance causing it to be very memory inefficient. 

6. What is a “closure” in JavaScript? Provide an example.

An inner function that has access to the variables of an outer function even if those variables were returned.

function careerInfo (career) {
	var jobInfo = “I work as a ”;
	function makeString(){
		return jobInfo + career
	}
	return makeString
}

careerInfo(“developer”);

7. Write a mul function which will produce the following outputs when invoked.
```javascript
console.log(mul(2)(3)(4)); // output : 24 
console.log(mul(4)(3)(4)); // output : 48
```

    function mult(a,b,c){
        return ((a * b) * c)
    }

8. How would you empty an array in JavaScript? Provide at least 2 methods of doing so.

Var x = [1, 2, 3, 4, 5];
X = [];

Var x = [1, 2, 3, 4, 5];
x.split(0, x.length);

9. What will be the output of the following code?
```javascript
var output = (function(x){
    delete x;
    return x;
  })(0);
  
  console.log(output);
```
    0

What about this code?
```javascript
var x = 1;
var output = (function(){
    delete x;
    return x;
  })();
  
  console.log(output);
```
    1

And what about this one?
```javascript
var x = { foo : 1};
var output = (function(){
    delete x.foo;
    return x.foo;
  })();
  
  console.log(output);
```
    Undefined

And finally, what about this one?
```javascript
var Employee = {
  company: 'xyz'
}
var emp1 = Object.create(Employee);
delete emp1.company
console.log(emp1.company);
```
    xyz

10. What would this code return?
```javascript
var trees = ["xyz","xxxx","test","ryan","apple"];
delete trees[3];
  
  console.log(trees.length);
```
    5

11. What will be the output of the code below?
```javascript
var bar = true;
console.log(bar + 0);   
console.log(bar + "xyz");  
console.log(bar + true);  
console.log(bar + false);   
```
    1
    truexyz
    2
    1

12. What will be the output of the code below?
```javascript
var z = 1, y = z = typeof y;
console.log(y);  
```
undefined

13. What would be the output of the code below?
```javascript
 var salary = "1000$";

 (function () {
     console.log("Original salary was " + salary);

     var salary = "5000$";

     console.log("My New Salary " + salary);
 })();

```

Original salary was undefined
My New Salary 5000$

14. What is the instanceof operator in JavaScript? What would be the output of the code below?
```javascript
function foo(){ 
  return foo; 
}
new foo() instanceof foo;
```

False

15. What constitutes a "Primitive" value in Javascript?

	A value that has no properties. Examples include numbers, strings, booleans, undefined, and null

16. What is the difference between a reference type variable and a value type variable?

	Reference type variables are objects and arrays while value type variables are similar to primitives. 

17. How would you describe the difference between class-based inheritance and prototypical inheritance?

prototypal inheritance is when an object inherits from another object while classical inheritance class inherits from another class.

## ES6 Questions

1. What is the difference between JavaScript and ECMAScript?

	ECMAscript is programming language standard while javascript is a programming language based off ECMAscript.

2. What do `const` and `let` do? And when would we use them?

	Const defines a variable but does not allow the variable’s value to be changed. Let defines a variable in block scope. 

3. How would you describe the difference between `function` and `function*`?

function* creates a generator function which is a function that can be exited and rentered later. 
	
4. When would you NOT use an arrow function in the place of a regular function expression?

	If you do not want to bind ‘this’

5. Refactor the following code to use an ES6 Template Literal.
```javascript
var name = 'Tiger';
var age = 13;

console.log('My cat is named ' + name + ' and is ' + age + ' years old.');
```
console.log(`My cat is named ${name} and is ${age} years old`);

6. How would you refactor the following code to use ES6 default parameters?
```javascript
function addTwoNumbers(x, y) {
    x = x || 0;
    y = y || 0;
    return x + y;
}
```

var addTwoNumbers = (x = 0, y = 0) => x + y

7. What is a "Promise" in ES6? And how many different states do they have?

A promise represents the eventual result of an asynchronous operation. They have 3 states of pending, resolved, and rejected

8. What is a practical use case for Promises? 

	When doing an AJAX request to make sure you are getting data back from your request. 

9. What is wrong with the following code? And how could it be better?
```javascript
new Promise((resolve, reject) => {  
  throw new Error('error')
}).then(console.log)
```
There is no error to be thrown so the promise is never fulfilled.
10. Describe the .fetch() method. What is one disadvantage to using the .fetch() method over existing methods?

	The fetch method allows us to make AJAX requests over the internet. 

## Node.js Questions

1. What is Node.js?

Node.js is a platform built on Chrome's JavaScript runtime for easily building fast and scalable network applications

2. What is an "Error-First" Callback?

	A protocol in node where the error object should be the first callback. If the response is null then the function completes. 

3. What is the Node.js Event Loop?

The Node.js event loop runs under a single thread, this means the application code you write is evaluated on a single thread.

4. Why might someone choose to use the Node.js Async single-threaded model over a more traditional multi-threaded model?

	Because it is less cpu intensive. 

5. What is meant by the term "non-blocking I/O"?

	Refers to code that does not run in a ‘synchronous’ fashion making programs faster and more efficient. 

6. What is the "memory stack"? And what happens when you exceed it?

The stack is where memory is allocated for automatic variables within functions. If you exceed it you will receive a segmentation fault.

## React.js Questions

1. What makes React.js more efficient at updating the DOM?

	It uses a virtual DOM which lets us rerender the screen on the fly. 
2. What is the difference between a Logical component and a Pure component?

	Pure components do not attempt to change their inputs and always return the same results. Logical components are based off of conditional rendering. 

3. What happens when you call "setState" in React?

	It sets the state and tells react that this component and its children need to be rerendered. 

4. What is the React method to create a component? Alternatively, how would you accomplish the same thing using ES6 classes?

Var someCoponent = React.createClass({});

Class someCoponent extends Component { }

5. In which React lifecycle event would you make AJAX requests? And why?

componentWillMount

6. Why would you use `React.Children.map(props.children, () => )` instead of `props.children.map(() => )`?

	This way the props get sent down to the children.

7. What is JSX?

	 A preprocessor that adds XML syntax to javascript. 

## Internet/Network Questions

1. What does TCP/IP stand for?

Transmission Control Protocol/Internet Protocol

2. Behind the scenes, how does HTTPS differ from HTTP?

	HTTPS is a secure version of HTTP where all your communications between your browser and website are encrypted. 

3. Define the general response status code categories.

	1 - Informational Response
	2 - Success
3 - Redirection
4 - Client errors
5 - Server errors
 
4. What does DDOS stand for?

	Distributed Denial of Service 

5. What is CORS? How does it work?

Cross-origin resource sharing

used to get around the browsers same-origin policy. For security purposes, a browser won't load requests for resources to other domains when those requests are initated by scripts.

6. What does REST stand for when we refer it in the context of a "RESTful API"? 

	Representational State Transfer

	An API is RESTful when when it doesn’t require the client to know anything about its structure. The server just provides whatever information the client needs to interact with the service.

## Resources

https://blog.risingstack.com/node-js-interview-questions-and-answers-2017/
https://www.codementor.io/nihantanu/21-essential-javascript-tech-interview-practice-questions-answers-du107p62z
https://github.com/DrkSephy/es6-cheatsheet
http://career.guru99.com/top-25-interview-questions-on-node-js/
https://tylermcginnis.com/react-interview-questions/
https://hackernoon.com/19-things-i-learnt-reading-the-nodejs-docs-8a2dcc7f307f
http://wesbos.com/arrow-function-no-no/
https://github.com/indy256/Full-stack-Developer-Interview-Questions-and-Answers
https://github.com/arialdomartini/Back-End-Developer-Interview-Questions
https://github.com/h5bp/Front-end-Developer-Interview-Questions


