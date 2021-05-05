Pattern: Use of `setTimeout/setInterval` in `asyncData/fetch`

Issue: -

## Description

This rule is for preventing using `setTimeout/setInterval` in `asyncData/fetch` since it may lead to memory leak.

Examples of **incorrect** code for this rule:

```js
export default {
  asyncData() {
    let foo = 'bar'
    setTimeout(() => {
      foo = 'baz'
    }, 0)
  },
  fetch() {
    let foo = 'bar'
    setInterval(() => {
      foo = 'baz'
    }, 0)
  }
}

```

Examples of **correct** code for this rule:

```js
export default {
  async asyncData() {
    let foo = 'baz'
  },
  fetch() {
    let foo = 'baz'
  }
}

```

## Further Reading

* [GitHub - nuxt/no-timing-in-fetch-data](https://github.com/nuxt/eslint-plugin-nuxt/blob/master/docs/rules/no-timing-in-fetch-data.md)