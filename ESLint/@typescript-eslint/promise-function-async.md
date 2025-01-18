Pattern: Promise-returning function without async

Issue: -

## Description

Functions that return Promises but aren't marked as `async` can be harder to maintain as they can either return a rejected promise or throw an Error. This ambiguity requires error handling code to handle both cases. Marking such functions as `async` ensures consistent error handling through the Promise rejection path.

## Examples

Example of **incorrect** code:
```ts
const arrowFunctionReturnsPromise = () => Promise.resolve('value');

function functionReturnsPromise() {
  return Promise.resolve('value');
}

function functionReturnsUnionWithPromiseImplicitly(p: boolean) {
  return p ? 'value' : Promise.resolve('value');
}

class Example {
  methodReturnsPromise() {
    return new Promise(resolve => resolve('value'));
  }
}
```

Example of **correct** code:
```ts
const arrowFunctionReturnsPromise = async () => Promise.resolve('value');

async function functionReturnsPromise() {
  return Promise.resolve('value');
}

// Explicit return type allows non-async
function mixedReturnType(): string | Promise<string> {
  return Math.random() > 0.5 ? 'value' : Promise.resolve('value');
}

class Example {
  async methodReturnsPromise() {
    return new Promise(resolve => resolve('value'));
  }
}
```