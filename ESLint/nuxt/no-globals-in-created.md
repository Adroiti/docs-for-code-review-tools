Pattern: Use of `window/document` in `created/beforeCreate`

Issue: -

## Description

This rule is for preventing using `window/document` in `created/beforeCreate`, since `created/beforeCreate` may be executed in server side in SSR.

Examples of **incorrect** code for this rule:

```js

export default {
  created() {
    window.foo = 'bar'
  }
}

```

Examples of **correct** code for this rule:

```js

export default {
  created() {
    const foo = 'bar'
  }
}

```

## Further Reading

* [GitHub - nuxt/no-globals-in-created](https://github.com/nuxt/eslint-plugin-nuxt/blob/master/docs/rules/no-globals-in-created.md)