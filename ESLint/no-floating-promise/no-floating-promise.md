Pattern: Missing `await` on `async` function call

Issue: -

## Description

Promises that are never awaited can cause unexpected behavior because they may be scheduled to execute at an unexpected time.

Examples of **incorrect** code for this rule:

```js
function writeToDb() {
  // synchronously write to DB
}
writeToDb();
```

Examples of **correct** code for this rule:

```js
async function writeToDb() {
  // asynchronously write to DB
}
writeToDb(); // <- note we have no await here but probably the user intended to await on this!
```

## Further Reading

* [eslint-plugin-no-floating-promise](https://github.com/SebastienGllmt/eslint-plugin-no-floating-promise?tab=readme-ov-file#rule-details)
