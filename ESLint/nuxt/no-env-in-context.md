Pattern: Use of `context.isServer/context.isClient` in `asyncData/fetch/nuxtServerInit`

Issue: -

## Description

This rule is for preventing using `context.isServer/context.isClient` in `asyncData/fetch/nuxtServerInit`.

Examples of **incorrect** code for this rule:

```js

export default {
  asyncData(context) {
    if (context.isServer) {
      const foo = 'bar'
    }
  },
  fetch({ isClient }) {
    if (isClient) {
      const foo = 'bar'
    }
  }
}

```

Examples of **correct** code for this rule:

```js

export default {
  async asyncData() {
    if (process.server) {
      const foo = 'bar'
    }
  },
  fetch() {
    if (process.client) {
      const foo = 'bar'
    }
  }
}

```

## Further Reading

* [GitHub - nuxt/no-env-in-context](https://github.com/nuxt/eslint-plugin-nuxt/blob/master/docs/rules/no-env-in-context.md)