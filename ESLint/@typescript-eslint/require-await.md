Pattern: Async function without await

Issue: -

## Description

Marking a function as `async` without using `await` inside it or returning a Promise is unnecessary and can be misleading. These functions can be rewritten as regular synchronous functions unless they need to handle Promises or use `await` expressions.

## Examples

Example of **incorrect** code:
```ts
async function returnNumber() {
  return 1;
}

async function* asyncGenerator() {
  yield 1;
}

const arrowAsync = async () => {
  const x = 1;
  return x;
};

class Example {
  async method() {
    return 'value';
  }
}
```

Example of **correct** code:
```ts
function returnNumber() {
  return 1;
}

function* syncGenerator() {
  yield 1;
}

const arrowSync = () => {
  const x = 1;
  return x;
};

async function withAwait() {
  const result = await somePromise();
  return result;
}

async function returnPromise() {
  return Promise.resolve('value');
}
```