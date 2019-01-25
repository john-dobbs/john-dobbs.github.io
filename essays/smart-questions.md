---
layout: essay
type: essay
title: Smart Questions
# All dates must be YYYY-MM-DD format!
date: 2019-01-24
labels:
  - Learning
---

“There’s no such thing as a stupid question”, a common phrase used by teachers around the world, but after reading [How To Ask Questions The Smart Way](http://www.catb.org/esr/faqs/smart-questions.html), one has to ask, are there stupid questions?

## What is a “Smart” Question?


### Example
<blockquote>
  “I have been processing some client side data which may be up to 100MB in total. I have been using a global variable to store the data and the variable is declared at the top of my JS file:
```
var data = null;
```
Followed by the definition, there are some functions that load data to this variable, such as:

data = new Object();
data.array = [];
for (var i=0;i<10000;i++){
  data.array[i] = i;
}
Then some operations will replace the data.array with some new data. I found that if I just set null to data before loading the new data, the memory of the browser will growing very fast:

data = null;
data = something_new;
data.array = something_new;
So I tried to use delete before loading new data:

delete data.array;
Now I have a question: do I have to delete each of the element in data.array or can I just delete the whole array using delete data.array; ? Thanks!”
  <footer><a href="https://stackoverflow.com/questions/33382997/how-to-release-memory-of-javascript-variables-correctly">HQXU85 on StackOverflow</a></footer>
</blockquote>

### Counter Example
<blockquote>
  “What is the difference between == and === in JavaScript? I have also seen != and !== operators. Are there more such operators?”
  <footer><a href="https://stackoverflow.com/questions/523643/difference-between-and-in-javascript">Shiva on StackOverflow</a></footer>
</blockquote>
Having gone through a few programming courses, I know that the answer to this question is covered when going over conditional statements; I can only assume that this person is either not paying attention in class or attempting to skip some reading assignments.  To add to their laziness, they did not even take the time to search for the answer before posting their question, since someone had already posted the same question to StackOverflow.


