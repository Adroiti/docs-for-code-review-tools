Pattern: Array sort without compare function

Issue: -

## Description

Without a compare function, `Array#sort()` and `Array#toSorted()` convert elements to strings and compare their UTF-16 code units. This leads to unexpected results, especially with numbers, where "10" comes before "2". Using sort without a compare function can create incorrect ordering in arrays.

## Examples

Example of **incorrect** code:
```ts
const array: any[];
const stringArray: string[];

array.sort();

// Even string arrays should use localeCompare
stringArray.sort();

[1, 2, 3, 10, 20, 30].sort(); // -> [1, 10, 2, 20, 3, 30]
```

Example of **correct** code:
```ts
const array: any[];

array.sort((a, b) => a - b);
array.sort((a, b) => a.localeCompare(b));

stringArray.sort((a, b) => a.localeCompare(b));

[1, 2, 3, 10, 20, 30].sort((a, b) => a - b); // -> [1, 2, 3, 10, 20, 30]
```