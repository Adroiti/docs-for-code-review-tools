Pattern: Object stringification without custom toString() method

Issue: -

## Description

When objects are stringified (via string concatenation, template literals, or String constructor), JavaScript calls toString(). Without a custom toString() method, objects default to "[object Object]" which is rarely the intended output and can mask important information.

## Examples

Example of **incorrect** code:
```ts
// String concatenation with default toString
'' + {};

// Template literals with default toString
class MyClass {}
const value = new MyClass();
`Value: ${value}`;

// Explicit calls to default methods
({}).toString();
({}).toLocaleString();

// Array join with objects using default toString
[{}, new MyClass()].join('');
```

Example of **correct** code:
```ts
// These types have meaningful toString methods
'Text' + true;
`Value: ${123}`;
`Arrays too: ${[1, 2, 3]}`;
(() => {}).toString();

// Custom toString implementation
class CustomToString {
  toString() {
    return 'Hello, world!';
  }
}
`Value: ${new CustomToString()}`;

// Object literal with toString
const literalWithToString = {
  toString: () => 'Hello, world!',
};
`Value: ${literalWithToString}`;

// Use JSON.stringify for objects without toString
const obj = { key: 'value' };
`Object: ${JSON.stringify(obj)}`;
```