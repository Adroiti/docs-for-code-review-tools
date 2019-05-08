Pattern: Inconsistent newline for dot

Issue: -

## Description

JavaScript allows you to place newlines before or after a dot in a member expression.

Consistency in placing a newline before or after the dot can greatly increase readability.

```js
var a = universe.
        galaxy;

var b = universe
       .galaxy;
```

## Further Reading

* [eslint-plugin-vue - dot-location](https://eslint.vuejs.org/rules/dot-location.html)
