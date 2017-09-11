Pattern: For-in loop over array

Issue: -

## Description

Disallows iterating over an array with a for-in loop.

A for-in loop (`for (var k in o)`) iterates over the properties of an Object.

While it is legal to use for-in loops with array types, it is not common. for-in will iterate over the indices of the array as strings, omitting any “holes” in the array.

More common is to use for-of, which iterates over the values of an array. If you want to iterate over the indices, alternatives include:

```ts
array.forEach((value, index) => { … }); 

for (const [index, value] of array.entries()) { … } 

for (let i = 0; i < array.length; i++) { … }
```

## Further Reading

* [TSLint - no-for-in-array](https://palantir.github.io/tslint/rules/no-for-in-array)