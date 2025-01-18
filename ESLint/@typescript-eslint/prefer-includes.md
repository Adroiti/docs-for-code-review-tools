Pattern: indexOf comparison over includes method

Issue: -

## Description

Using `indexOf` with comparison against -1 to check for value existence is less readable and more error-prone than using the `includes` method. Modern JavaScript provides `String.includes()` (ES2015) and `Array.includes()` (ES2016) as clearer alternatives for checking value existence.

## Examples

Example of **incorrect** code:
```ts
const str: string;
const array: any[];

str.indexOf(value) !== -1;
array.indexOf(value) !== -1;
typedArray.indexOf(value) > -1;
maybe?.indexOf('') !== -1;
userDefined.indexOf(value) >= 0;

// Using regex test for simple string checks
/example/.test(str);
```

Example of **correct** code:
```ts
const str: string;
const array: any[];

str.includes(value);
array.includes(value);
typedArray.includes(value);
maybe?.includes('');
userDefined.includes(value);

// Using string includes instead of regex
str.includes('example');
```