# Meteor-code-guidelines
We use [google's javascript guidelines](https://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)

Exceptions to google's styleguide:
- var:
    - Google's rule applies with the exception of globals. When defining a global you should leave out the var so the Meteor framework will make the variable globally accessible
- Custom Exceptions:
    - Use Meteor.error﻿
- Delete:
    - We use delete because it's more explicit of what it is doing and it feels like premature optimisation to reassign to null
- for-in-loop:
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
