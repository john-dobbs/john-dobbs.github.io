---
layout: essay
type: essay
title: JavaScript var vs. let
# All dates must be YYYY-MM-DD format!
date: 2019-01-18
labels:
  - JavaScript
  - Learning
---

In this post, I’m going to explain my stance against a new feature in JavaScript ECMAScript 6 (ES6), the let and const keywords, with regards to web development.  let and const allow for block scope variables/constants in JavaScript, but is such a feature necessary for a website?

Before going further, let’s quickly go over the basics of scope.  Before ES6, JavaScript only had two levels of scope, global scope and function scope:
```
var i = 2019; // global scope
function myFunction() {
  var j = 2020; // function scope
  console.log(i); // 2019
  console.log(j); // 2020
}
myFunction();
console.log(i); // 2019
console.log(j); // undefined
```
Notice that the variable j is undefined outside of myFunction.  Since ES6, variables declared with the let and const keywords have block scope:
```

```
Notice that variables...

Why use let and const instead of var?  Great question, but answers are usually vague, “let is block-scoped rather than function-scoped like var” (AirBNB JavaScript Style Guide, https://github.com/airbnb/javascript), so I turned to Google for some examples.

Hoisting
Without getting into too much detail since the topic is covered extensively elsewhere, hoisting is when a variable declaration is moved up to the top of the current scope.  Consider the following:
```

```
JavaScript interprets this as the following:
```

```
If the let keyword is used instead, an error would be thrown, as “expected”:
```

```
I consider this to be an edge case that could be easily avoided by properly formatting your code.

Loops
Consider the following for loop:
[insert code]
Apparently having the variable defined after the loop is an issue, but we can fix that using let:
[insert code]
Again, an edge case, if I were to use the variable i again, chances are it would be in another loop with initial values set accordingly.

Reduce Memory Usage
The use of block level variables could reduce memory usage, I like the sound of that, but let’s look at a possible application of this:
[insert code]
The above code frees the memory associated with the variable arr after the data is no longer needed, this could be useful for processing large amounts of data, but the focus of this article is web development, how often is a website going to send a bunch of raw data to a client for processing, not often.

Browser Support
Browser support is a concern for any website.  According to [caniuse.com](https://caniuse.com/#search=let), roughly 10% of global internet users have a browser that does not support the let keyword.  JavaScript is often used throughout the checkout process for input validation, of all the reasons for someone to abandon the checkout process, an unresponsive page because of using let instead of var should not be one of them.


