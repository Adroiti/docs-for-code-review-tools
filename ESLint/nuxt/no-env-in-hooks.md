Pattern: Use of `process.server`/`process.client`/`process.browser` in client-only hooks 

Issue: -

## Description

This rule is for preventing using `process.server`/`process.client`/`process.browser` in client only Vue lifecycle hooks since they're only executed in client side.

Examples of **incorrect** code for this rule:

```js

export default {
  mounted() {
    if (process.server) {
      const foo = 'bar'
    }
  },
  beforeMount() {
    if (process.client) {
      const foo = 'bar'
    }
  },
  beforeDestroy() {
    if (process.browser) {
      const foo = 'bar'
    }
  }
}

```

Examples of **correct** code for this rule:


```js

export default {
  mounted() {
    const foo = 'bar'
  },
  beforeMount() {
    const foo = 'bar'
  },
  beforeDestroy() {
    const foo = 'bar'
  }
}

```

## Further Reading

* [GitHub - nuxt/no-env-in-hooks](https://github.com/nuxt/eslint-plugin-nuxt/blob/master/docs/rules/no-env-in-hooks.md)