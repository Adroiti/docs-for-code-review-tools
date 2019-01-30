Pattern: Malformed semicolon for class property

Issue: -

## Description

This rule enforces consistent use of semicolons for class properties.

## Options

This rule has a single string optio:

* `"always"` (default) requires semicolons at the end of a class property
* `"never"` disallows semicolons as the end of a class property

### always

Examples of **incorrect** code for this rule with the default `"always"` option:

```js
/*eslint class-property/class-property-semicolon: ["error", "always"]*/

class MyClass {
    classProperty = 'foo'
}
```

Examples of **correct** code for this rule with the default `"always"` option:

```js
/*eslint class-property/class-property-semicolon: ["error", "always"]*/

class MyClass {
    classProperty = 'foo';
}
```

### never

Examples of **incorrect** code for this rule with the `"never"` option:

```js
/*eslint class-property/class-property-semicolon: ["error", "never"]*/

class MyClass {
    classProperty = 'foo';
}
```

Examples of **correct** code for this rule with the `"never"` option:

```js
/*eslint class-property/class-property-semicolon: ["error", "never"]*/

class MyClass {
    classProperty = 'foo'
}
```