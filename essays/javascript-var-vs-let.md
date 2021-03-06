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

## To <i>let</i> or Not to <i>let</i>
In this post, I’m going to explain my stance against using a new feature in JavaScript ECMAScript 6 (ES6), the <i>let</i> and <i>const</i> keywords, with regards to web development.  <i>let</i> and <i>const</i> allow for block scope variables/constants in JavaScript, but is such a feature necessary for a website?

Before going further, let’s quickly go over the basics of scope.  Before ES6, JavaScript only had two levels of scope, global scope and function scope ([JSFiddle](http://jsfiddle.net/jmd386/v93t0rqo/)):
```javascript
var i = 2019;     // global scope
function myFunction() {
  var j = 2020;   // function scope
  console.log(i); // 2019
  console.log(j); // 2020
}
myFunction();
console.log(i);   // 2019
console.log(j);   // undefined
```
Notice that the variable j is undefined outside of myFunction.  Since ES6, variables declared with the <i>let</i> and <i>const</i> keywords have block scope ([JSFiddle](http://jsfiddle.net/jmd386/y45uc0zn/)):
```javascript
let i = 2019;       // global scope
function myFunction() {
  let j = 2020;     // function scope
  console.log(i);   // 2019
  console.log(j);   // 2020
  {
    let i = 2021;   // block scope
    j = 2021;       // modifies function scope
    let k = 2021;   // block scope
    console.log(i); // 2021
    console.log(j); // 2021
    console.log(k); // 2021
  }
  console.log(i);   // 2019
  console.log(j);   // 2021
  console.log(k);   // undefined
}
myFunction();
console.log(i);     // 2019
console.log(j);     // undefined
console.log(k);     // undefined
```
Notice that variables declared using the <i>let</i> keyword behave similarly to variables declared using the <i>var</i> keyword in global scope and function scope (when placed at the top of the function block).  Also notice that variables can be redeclared within a sub-block using <i>let</i> and that any changes to a redeclared variable do not apply to the variable outside of the sub-block.

## Why Use <i>let</i> and <i>const</i> Instead of var?
Great question, but answers are usually vague, such as “<i>let is block-scoped rather than function-scoped like var</i>” ([AirBNB JavaScript Style Guide](https://github.com/airbnb/javascript#references--disallow-var)), so I turned to Google for some examples.

## Hoisting
Without getting into too much detail since the topic is covered extensively elsewhere, hoisting is when a variable declaration is moved up to the top of the current scope.  Consider the following ([JSFiddle](http://jsfiddle.net/jmd386/2xf5v1q7/)):
```javascript
function myFunction() {
  var i = 2019;
  console.log(i); // 2019
  console.log(j); // undefined, but no error
  var j = 2020;
}
myFunction();
```
JavaScript interprets this as ([JSFiddle](http://jsfiddle.net/jmd386/v43dgc27/)):
```javascript
function myFunction() {
  var i = 2019;
  var j;          // hoisted declaration
  console.log(i); // 2019
  console.log(j); // undefined, but no error
  j = 2020;       // assignment
}
myFunction();
```
If the <i>let</i> keyword is used instead, an error would be thrown, as “expected” ([JSFiddle](http://jsfiddle.net/jmd386/bh690Les/)):
```javascript
function myFunction() {
  let i = 2019;
  console.log(i); // 2019
  console.log(j); // undefined
  let j = 2020;
}
myFunction();
```
I consider this to be an edge case that could be easily avoided by properly formatting your code.

## Loops
Consider the following for loop ([JSFiddle](http://jsfiddle.net/jmd386/zta7f2sb/)):
```javascript
function myFunction() {
  for (var i = 0; i < 10; i++) {
    console.log(i); // 0, 1, 2, ... 9
  }
  console.log(i);   // 10
}
myFunction();
```
The variable <i>i</i> is still defined after the loop, but we can fix that using <i>let</i> ([JSFiddle](http://jsfiddle.net/jmd386/94jodyaf/)):
```javascript
function myFunction() {
  for (let i = 0; i < 10; i++) {
    console.log(i); // 0, 1, 2, ... 9
  }
  console.log(i);   // undefined
}
myFunction();
```
Again, an edge case, does it matter if the variable <i>i</i> is still defined after the loop?

## Memory Usage
The use of block level variables could reduce memory usage.  I like the sound of that, but let’s look at a possible application of this ([JSFiddle](http://jsfiddle.net/jmd386/4krca03b/)):
```javascript
function myFunction() {
  let sum = 0;
  {
    let arr = [];
    // fill array with data
    // possibly from a JSON file or an AJAX request, or a for loop in this case
    for (let i = 0; i < 1000000; i++) {
      arr[i] = i;
    }
    for (let i = 0; i < arr.length; i++) {
      sum += arr[i];
    }
  }
  console.log(arr); // undefined, no longer in memory!
  // do something with sum
  console.log(sum);
}
myFunction();
```
The above code frees the memory associated with the variable <i>arr</i> after the data is no longer needed, i.e. after the block.  This could be useful for processing large amounts of data, but how often is a website going to send a bunch of raw data to a client for processing?

## Browser Support
Browser support is a concern for any website.  According to [caniuse.com](https://caniuse.com/#search=let), roughly 10% of global internet users have a browser that does not support the <i>let</i> keyword (as of January 2019).  JavaScript is often used throughout the checkout process for input validation, of all the reasons for someone to abandon the checkout process, an unresponsive page because of using <i>let</i> instead of <i>var</i> should not be one of them.  Taking the world's largest online retailer as an example, looking at the JavaScript sent to your browser shows the use of <i>var</i>, not <i>let</i>.

## <span style="text-decoration: line-through">To <i>let</i> or</span> Not to <i>let</i>
Although there are a few benefits to using the <i>let</i> and <i>const</i> keywords, I do not believe those benefits to be useful for web development purposes.  Most of the benefits I was able to find were edge cases, easily fixable by following a few formatting rules; the one exception being the memory usage, which could be fixed by creating a separate function for any memory intensive operations.


