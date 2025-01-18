Pattern: Inconsistent promise return style

Issue: -

## Description

The choice to use `return await` or just `return` for promises affects error handling and stack traces. Inside try-catch blocks, returning a promise without await will prevent catch blocks from catching rejections. Additionally, awaiting promises before returning them improves stack trace information, making debugging easier.

## Examples

Example of **incorrect** code:
```ts
// Inside try-catch, promise rejection won't be caught
async function incorrect1() {
  try {
    return Promise.reject('error');
  } catch (e) {
    // Never executes
  }
}

// Unnecessary awaits outside try-catch
async function incorrect2() {
  return await Promise.resolve('value');
}

// Missing await in using statement scope
async function incorrect3() {
  using resource = getResource();
  return Promise.reject('error');
}
```

Example of **correct** code:
```ts
// Inside try-catch, await catches rejections
async function correct1() {
  try {
    return await Promise.reject('error');
  } catch (e) {
    // Handles error
  }
}

// Direct return outside try-catch
async function correct2() {
  return Promise.resolve('value');
}

// Await in using statement scope
async function correct3() {
  using resource = getResource();
  return await Promise.reject('error');
}
```