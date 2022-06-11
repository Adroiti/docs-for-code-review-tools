Pattern: Value assigned to `module` variable

Issue: -

## Description

A value is being assigned to the `module` variable. The `module` variable is already used and it is highly likely that assigning to this variable will cause errors.

### Possible Ways to Fix It

Use a different variable name:

```jsx
let myModule = {...}
```

## Further Reading

* [next.js - No assign module variable](https://nextjs.org/docs/messages/no-assign-module-variable)