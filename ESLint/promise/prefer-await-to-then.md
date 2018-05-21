Pattern: Use of `then()` instead of `await`

Issue: -

## Description

Prefer `await` to `then()` for reading Promise values.

Example of **correct** code:

```js
async function example() {
  let val = await myPromise()
  val = doSomethingSync(val)
  return doSomethingElseAsync(val)
}

async function exampleTwo() {
  try {
    let val = await myPromise()
    val = doSomethingSync(val)
    return await doSomethingElseAsync(val)
  } catch (err) {
    errors(err)
  }
}
```

Example of **incorrect** code:

```js
function example() {
  return myPromise.then(doSomethingSync).then(doSomethingElseAsync)
}

function exampleTwo() {
  return myPromise
    .then(doSomethingSync)
    .then(doSomethingElseAsync)
    .catch(errors)
}
```

## Further Reading

* [eslint-plugin-promise - prefer-await-to-then](https://github.com/xjamundx/eslint-plugin-promise/blob/master/docs/rules/prefer-await-to-then.md)