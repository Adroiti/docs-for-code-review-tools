Pattern: Promise misuse in conditional or void context

Issue: -

## Description

Promises can be misused in conditional contexts (if statements, boolean operations) or in contexts expecting void returns. This can lead to unexpected behavior because Promises are always truthy, and unhandled Promise returns can lead to difficult-to-debug race conditions.

## Examples

Example of **incorrect** code:
```ts
// Promise in if condition
async function check() {
  const promise = Promise.resolve(false);
  if (promise) {  // Always true
    console.log('runs');
  }
}

// Promise in logical operations
const value = Promise.resolve(123) || 'default';

// Async function in void-return context
[1, 2, 3].forEach(async item => {
  await processItem(item);  // Unhandled promise
});

// Promise in object spread
const obj = { ...Promise.resolve({ prop: 'value' }) };

// Async event handler without error handling
element.onclick = async () => {
  await submitForm();
};

// Async function in synchronous interface
interface SyncInterface {
  process(): void;
}
class Handler implements SyncInterface {
  async process() {  // Returns Promise<void> instead of void
    await doWork();
  }
}
```

Example of **correct** code:
```ts
// Awaited Promise in condition
async function check() {
  const promise = Promise.resolve(false);
  if (await promise) {
    console.log('might not run');
  }
}

// Proper Promise handling
const value = await Promise.resolve(123) || 'default';

// Proper async iteration
for (const item of items) {
  await processItem(item);
}

// Promise.all for parallel operations
await Promise.all(items.map(async item => {
  await processItem(item);
}));

// Proper error handling for async events
element.onclick = () => {
  submitForm().catch(handleError);
};

// Correct interface for async operations
interface AsyncInterface {
  process(): Promise<void>;
}
class Handler implements AsyncInterface {
  async process() {
    await doWork();
  }
}

// Proper object spread
const obj = { ...(await Promise.resolve({ prop: 'value' })) };
```