# Javascript guidelines
This guidelines apply to all javascript code in our meteor applications.

We use [google's javascript guidelines](https://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)

Ammendments to google's guideline:
- var
    - Google's rule applies with the exception of globals. When defining a global you should leave out the var so the Meteor framework will make the variable globally accessible
- Custom Exceptions
    - Use Meteor.error﻿
- Delete
    - We use delete because it's more explicit of what it is doing and it feels like premature optimisation to reassign to null
- for-in-loop
    - Don't do manual looping use underscore﻿ instead
- Naming
    - Properties and methods
        - We prefix privates with a _ instead of a trailing _.
- Method and function parameter
   - Specify optional parameters in jsdoc. But try to avoid them!
   - Do not use variable arguments.
   - Please avoid using the arguments array for anything other then passing the arguments on. Example:
   ```javascript
function a () {
	/*dostuff*/
	b.apply(this, arguments);
}
```
- Filenames
    - Do not use - only use _
- Custom toString() methods
    - Only create them when you have good reasons.
- Code formatting
	- Array and Object Initializers
		- Array and Object initialisation can only be in 1 line when its a simple Array or Object (no nesting)
	- Column limit
		- We do not enforce a hard column limit, use common sense.
	- Function Arguments
		- Avoid wrapping if you're arguments force you to wrap the function statement your argument names are probaply too long
		- Also avoid indenting the function call, unless you really really really have to.
	- Passing Anonymous Functions
      - When you need to wrap a function call with an anyonymous function store it in a variable first.
  - Binary and Ternary Operators
      - We do not have a hard column limit so must inline if's should fit in 1 row.
  - JavaScript Types
      - Google's guideline includes a lot of closure compiler specific stuff which can be ignored. However JSDOC should be accurate and should use their guideline.
  - Comments
      - All methods you touch or add should be documented with JSDoc
      - HTML in JSDoc
          - Please do not put HTML in JSDoc because it will make it less readable
  - Compiling
      - The Meteor framework handles the minifying/compiling of our application, no extra user actions are required.
  - Linting tool
      - Always enable JSHINT in your IDE and set it up to use the project's ```.jshintrc```





*TBD*
Change 4 soft tabs to 2 soft tabs?!
