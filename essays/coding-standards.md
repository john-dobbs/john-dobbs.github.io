---
layout: essay
type: essay
title: Going for Green
# All dates must be YYYY-MM-DD format!
date: 2019-02-07
labels:
  - Learning
---

Coding standards, you will either love them at first sight or curse the day someone required you use them, but I think they eventually grow on you.

## Beyond Tabs vs Spaces
Although an eternal debate among programmers, using tabs vs spaces is only scratching the surface of what coding standards entail, but it does make for great episode of Silicon Valley.  Coding standards cover all aspects of your code, from formatting, to layout, to naming conventions, and everything in between, all with the intention of improving the readability of your code and allowing it to be easily understood by others.  This can become incredibly useful when working on collaborative projects, even more so as the project size grows.

Looking back on my own experiences, over the years I subconsciously got in the habiting of following some simple formatting techniques that significantly improved the readability of my programs, which ultimately reduced the time to debug any issues.  Although following a coding standard is a rather new concept to me, I can see the benefits to using them.

## Impressions on IntelliJ IDEA and ESLint
For my Software Engineering course at UH Manoa, we just started using IntelliJ IDEA.  Although I have experience using Microsoft Visual Studio, using an IDE is another new concept for me, I’ve only used Visual Studio for compiling software I’ve programmed elsewhere.  Some features in IntelliJ IDEA are difficult to get used to when coming from another environment, such as automatically adding closing parentheses and brackets, auto-indenting and auto-complete… I can see these features being useful, especially for those just starting off programming, but it can also cause some confusion if you are not used to it.

Onward and upwards to ESLint, which is a JavaScripting coding standard.  Getting it to function properly on IntelliJ IDEA took quite a bit of work (for Windows at least), and once it is installed, the plugin is fairly temperamental.  IntelliJ IDEA will run the various ESLint tests as you program, which causes all sorts of useless errors to appear that will disappear once you get around to programming the next line or two.  One such example is declaring a variable, immediately an error is displayed alerting you to the fact that you haven’t used it anywhere; thank you captain obvious, I just finished declaring it.  Another issue is that IntelliJ IDEA will sometimes display a red “x” icon, which means that your code did not pass the ESLint tests, but upon moving your curser over top of the icon, it will change to a green check mark icon, which means that your code passed the ESLint tests.

## Going for Green Check Marks
Moving past some of the issues with implementation, I can see many benefits to having the ESLint tests automatically run on your code.  One such benefit is that you fix your code as you code, as opposed to coming back to it hours or days later and having to remember what your thought process was at the time.  The ESLint standard includes formatting guidelines, so another benefit is nicely formatted code, which can help to spot issues when debugging.  I am also a big fan of visual indicators, so seeing a green check mark to let me know my code meets the coding standard is a nice feature (if only it updated properly).  All in all, I find coding standards to be very useful and believe that programming classes should do more to emphasize their importance to those just starting off.




