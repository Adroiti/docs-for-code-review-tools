Pattern: Spread operator misuse on special types

Issue: -

## Description

Using the spread operator on certain types like Promises, functions, iterables, or class instances can lead to unexpected behavior. The spread operator only copies enumerable own properties, which means it may not properly handle class inheritance, async values, or iterable objects.

## Examples

Example of **incorrect** code:
```ts
// Spreading Promise without await
const promise = new Promise(resolve => resolve(123));
const spread = { ...promise };

// Spreading function without call
function getData() { return { x: 1 }; }
const obj = { ...getData };

// Spreading Map/Set into object
const map = new Map([['key', 'value']]);
const mapSpread = { ...map };

// Spreading string into array
const str = 'hello';
const chars = [...str];

// Spreading class or instance
class Box {
  value = 123;
  getValue() { return this.value; }
}
const boxSpread = { ...Box };
const instance = new Box();
const instanceSpread = { ...instance };
```

Example of **correct** code:
```ts
// Await Promise before spread
const promise = new Promise(resolve => resolve(123));
const spread = { ...(await promise) };

// Call function before spread
function getData() { return { x: 1 }; }
const obj = { ...getData() };

// Convert Map to Object
const map = new Map([['key', 'value']]);
const mapObj = Object.fromEntries(map);

// Split string into characters
const str = 'hello';
const chars = str.split('');

// Properly clone instance
class Box {
  value = 123;
  getValue() { return this.value; }
}
const instance = new Box();
const copy = new Box();
Object.assign(copy, instance);
```