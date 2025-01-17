Pattern: Redundant void operator usage

Issue: -

## Description

Using the void operator on expressions that are already of type void or undefined is unnecessary and can make code harder to understand. The void operator should only be used when explicitly discarding a value that would otherwise be used.

## Examples

Example of **incorrect** code:
```ts
// void on function returning void
function noReturn() {}
void noReturn();

// void on undefined expression
void undefined;

// void on void-returning arrow function
const voidReturn = () => {};
void voidReturn();

// void on void Promise
async function voidPromise() {}
void voidPromise();

// Multiple void operators
void void something;

// void on undefined variable
let x: undefined;
void x;
```

Example of **correct** code:
```ts
// void on function returning value
function getNumber() { return 42; }
void getNumber();

// void on Promise to indicate intentional non-handling
void Promise.resolve(123);

// void on expression with value
void (x + y);

// void in proper Promise non-handling
void async function() {
  await processThing();
};

// Direct call of void function
function noReturn() {}
noReturn();

// Proper undefined assignment
let x: undefined = undefined;
```