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
