Pattern: For-in loop used with array

Issue: -

## Description

Using for-in to iterate over an array can lead to unexpected behavior because it iterates over all enumerable properties, including prototype properties, and returns string indices. Additionally, it skips empty array slots and doesn't provide direct access to array values.

## Examples

Example of **incorrect** code:
```ts
// Basic for-in with array
const numbers = [1, 2, 3];
for (const i in numbers) {
  console.log(numbers[i]);
}

// For-in with type conversion
const items = ['a', 'b', 'c'];
for (const index in items) {
  const num = +index; // string to number conversion needed
  console.log(items[num]);
}

// For-in with sparse array
const sparse = [1, , 3];
for (const i in sparse) {
  console.log(sparse[i]); // skips empty slot
}
```

Example of **correct** code:
```ts
// For-of for values
const numbers = [1, 2, 3];
for (const number of numbers) {
  console.log(number);
}

// Traditional for loop for index access
const items = ['a', 'b', 'c'];
for (let i = 0; i < items.length; i++) {
  console.log(i, items[i]);
}

// forEach with index and value
const data = [1, 2, 3];
data.forEach((value, index) => {
  console.log(index, value);
});

// Array.entries() for both index and value
const pairs = ['a', 'b', 'c'];
for (const [index, value] of pairs.entries()) {
  console.log(index, value);
}

// Map for transformation
const numbers = [1, 2, 3];
const doubled = numbers.map(n => n * 2);
```