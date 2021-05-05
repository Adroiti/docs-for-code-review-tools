Pattern: Use of `this` in `asyncData/fetch`

Issue: -

## Description

This rule is for preventing using `this` in `asyncData/fetch`.

Examples of **incorrect** code for this rule:

```js

export default {
  ...foo,
  async asyncData() {
    if (this.$route.path === 'foo') {

    }
  }
}

```

Examples of **correct** code for this rule:

```js

export default {
  ...foo,
  async asyncData() {
    // no this
  }
}

```

## Further Reading

* [GitHub - nuxt/no-this-in-fetch-data](https://github.com/nuxt/eslint-plugin-nuxt/blob/master/docs/rules/no-this-in-fetch-data.md)