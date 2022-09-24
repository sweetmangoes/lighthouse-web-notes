# Lecture 1 - Overview, Function Objects Conditionals Loops (FOCAL), Dev Approach
<p> Instructor: Duy Tran 

Background: Computer science background, doing Masters in Applied in Computer Science, worked all over the place in USA, Canada, Vietnam 

Format: 
1. Introductions
2. Overview of the modules (i.e. weeks)

Notes provided by Instructor: 

## Github:
Most common commands: [a simple guide](https://up1.github.io/git-guide/index.html)
  * git status
  * git add .
  * git commit -m "message"
  * git remote -v (or add origin, rm origin)
  * git push
  * git pull

## Workflow:
* To create a git repository in a directory, run <i>" git init"</i>
* <i>"git status"</i> will show you which files have been changed in the working directory
* Use <i> "git diff"</i> to see what specifically was changed inside each file
* To add files to the staging area, use <i> "git add <filename> "</i> or <i> "git add . "</i> to add all changes
* Commit your changes using <i> "git commit -m 'a meaningful commit message' "</i>
* Finally, push your code to github using <i> "git push origin master or git push origin main "</i>. 
* NOTE: This workflow is great for solo coding projects. When you work as part of a team (such as during mid-terms and finals), you will use a more advanced workflow.

## Problem Solving: 
* Work incrementally, writing and then executing small amounts of code
  * Break the problem down into a series of smaller (and easier to understand) steps
  * Small segments of code allow us to more easily see where errors/bugs are in our code

* Use proper indentation
  * Indentation helps us to see how our code is nested (eg. which lines of code are inside the function or if statement)

``` js 
// no indentation
  const printArray = function (arr) {
  arr.forEach(function(element) {
  console.log(element);
  });
  };
  console.log('All done!');

  // proper indentation
  const printArray = function (arr) {
    arr.forEach(function(element) {
      console.log(element);
    });
  };
  console.log('All done!');
```
* Try to avoid copy/pasting code; type it out for yourself and try to understand what you are typing.

* Errors are your friends:
  * Try to decipher the error message before you Google it.
  * Errors help to show us where we made a mistake and being able to read them is a valuable skill.

## Logic Syntac Data (LSD)
* Logic: have I told the computer exactly what to do?
* Syntax: am I missing a curly brace?
* Data: do I have the data I think I do in the format I expect?

## Asking for Help

* Remember the 15 minute rule
* Tell mentors what is not working and what you've tried
* Google the error message/what you want to accomplish; make sure to add the programming language (eg. JavaScript) to your search term (eg. "remove elements from array javascript")
* [StackOverflow](https://stackoverflow.com/) is useful for seeing multiple possible solutions to a problem (DO NOT copy and paste)
* [Mozilla Developer Network (MDN)](https://developer.mozilla.org/en-US/)

## Advice
* Be curious
* Be disciplined
* Connect with people
* Be kind to yourself

## Useful Links
* [Mozilla Developer Network (MDN)](https://developer.mozilla.org/en-US/)
* [Node Documentation](https://nodejs.org/en/docs/)
* [Python Tutor](https://pythontutor.com/javascript.html#mode=edit)

</p>
