Pattern: Potentially falsey value in logical AND expression

Issue: -

## Description

Forbids the usage of potentially falsey string or number values in logical && expressions.
Oftentimes, these logical expressions are used in jsx to enable conditional rendering behavior.

However, one can encounter unexpected behavior when a 0 or empty string values is returned as the result of the expression and rendered accidentally.

Examples of **incorrect** code for this rule:

```js
// Potentially falsey strings are not allowed
let str = '';
<App>{str && <Foo />}</App>;

// Potentially falsey numbers are not allowed
let num = 0;
<App>{num && <Foo />}</App>;

// Includes types that may be a string or number
let thisOrThat: Record<any, any> | string | number;
<App>{thisOrThat && <Foo />}</App>;
```

Examples of **correct** code for this rule:

```js
// Coalescing to boolean is ok
let str = "Foo";
<App>{!!str && <Foo />}</App>;

// Turning into a boolean is ok
let str = "Foo";
<App>{Boolean(str) && <Foo />}</App>;

// Constant values are ok
const str = "Foo";
<App>{str && <Foo />}</App>;

// Constant values are ok
const num = 1;
<App>{num && <Foo />}</App>;
```

### Options

```ts
type Options = [
  {
    allowString?: boolean;
    allowNumber?: boolean;
  }
];

defaultOptions: [
  {
    allowString: false,
    allowNumber: false,
  },
];
```

## Further Reading

* [strict-logical-expressions](https://github.com/hluisson/eslint-plugin-jsx-expressions/blob/master/docs/rules/strict-logical-expressions.md)
