Pattern: Array element deletion using delete operator

Issue: -

## Description

Using the delete operator on array elements creates sparse arrays by leaving empty slots without adjusting the array length. This leads to unexpected behavior when iterating or accessing the array. Array methods like splice() should be used instead to properly remove elements.

## Examples

Example of **incorrect** code:
```ts
const numbers = [1, 2, 3, 4];
delete numbers[1]; // Creates [1, empty, 3, 4]

let array = ['a', 'b', 'c'];
delete array[0]; // Creates [empty, 'b', 'c']

// Length remains unchanged
console.log(array.length); // Still outputs 3
```

Example of **correct** code:
```ts
const numbers = [1, 2, 3, 4];
numbers.splice(1, 1); // Creates [1, 3, 4]

let array = ['a', 'b', 'c'];
array.splice(0, 1); // Creates ['b', 'c']

// Filter out elements
array = array.filter(item => item !== 'a');

// Remove and store element
const removed = array.splice(0, 1)[0];
```