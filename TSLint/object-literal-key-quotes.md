Pattern: Malformed quote style for literal property

Issue: -

## Description

Enforces consistent object literal property quote style.

Object literal property names can be defined in two ways: using literals or using strings. For example, these two objects are equivalent:

```ts
var object1 = { property: true };
```

```ts
var object2 = { "property": true };
```

In many cases, it doesn’t matter if you choose to use an identifier instead of a string or vice-versa. Even so, you might decide to enforce a consistent style in your code.

This rules lets you enforce consistent quoting of property names. Either they should always be quoted (default behavior) or quoted only as needed ("as-needed").

## Further Reading

* [TSLint - object-literal-key-quotes](https://palantir.github.io/tslint/rules/object-literal-key-quotes)