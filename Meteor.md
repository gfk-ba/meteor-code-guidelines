# Meteor guidelines

## Template helper naming

Always use a verb as a prefix to template helpers to distinguish between data and helpers.
Use `is` when the helper returns boolean, `get` otherwise.

Example:

```js
Template.example.helpers({
    isActive: function () {
        return this.status === 'active';
    },
    getPinkUnicorn: function () {
        return this.fetchPinkUnicorn();
    }
});
```

## Classes

Use `class="{{#if something}}selected{{/if}}"` to add classes,
so from the template it is obvious for a desinger what classes an element can get.
Moreover your helpers will be more reusable, you can use them to add other classes
on other elements, without creating another helper.
Use this for data and template helpers as well.

Example:

```html
<div class="friendList {{#if isEmpty}}hidden{{/if}}">
  <ul>
    {{#each friends}}
      <li class="{{#if closeFriend}}highlight{{/if}}">
        {{firstName}} {{lastName}}
      </li>
    {{/each}}
  </ul>
</div>
```

## Logging

Always add you package name to the `tag` when logging, this makes it easier to
find your messages. Also logging the `Core.Authentication.getSurveyId()` and `Core.Authentication.getUserId()`
would be preferred when logging errors. Here are some examples:

```javascript
Meteor.log.error('Some fatal error happend!', {
    package: 'import-manager'
    surveyId: Core.Authentication.getSurveyId(),
    userId: Core.Authentication.getUserId()
});

Meteor.log.warn('Hmmm, OK, this shouldn\'t happen... Lets leave a warning about it!', {
    package: 'import-manager'
    surveyId: Core.Authentication.getSurveyId(),
    userId: Core.Authentication.getUserId()
});

Meteor.log.info('Hey, this is just a note that that process returned with exit-code 0', {package: 'import-manager'});

Meteor.log.debug('This is just some hand information for when you are developing', {package: 'import-manager'});

```
