Pattern: Traditional for loop over for-of

Issue: -

## Description

Using traditional `for` loops with index variables to access array elements is more verbose and error-prone than using `for-of` loops when the index is only used to access the array elements. The `for-of` loop provides clearer syntax and eliminates potential off-by-one errors.

## Examples

Example of **incorrect** code:
```ts
declare const array: string[];

for (let i = 0; i < array.length; i++) {
  console.log(array[i]);
}

for (let i = 0; i < items.length; i++) {
  const item = items[i];
  process(item);
}
```

Example of **correct** code:
```ts
declare const array: string[];

for (const x of array) {
  console.log(x);
}

// Index is used for something other than array access
for (let i = 0; i < array.length; i++) {
  console.log(i, array[i]);
}

// Processing items with their indices
array.forEach((item, index) => {
  console.log(index, item);
});
```