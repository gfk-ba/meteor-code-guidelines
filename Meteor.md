# Meteor guidelines

## Template helpers

Always use a verb as a prefix to template helpers to distinguish between data and helpers.
Use `is` when the helper returns boolean, `get` otherwise.

Example:

```
Template.example.helpers({
    isActive: function () {
        return this.status === 'active';
    },
    getPinkUnicorn: function () {
        return this.fetchPinkUnicorn();
    }
});
```
