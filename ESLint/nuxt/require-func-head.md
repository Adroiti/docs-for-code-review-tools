Pattern: Use of non-fuction `head` property in component

Issue: -

## Description

This rule is enforcing `head` property in component to be a function.

Examples of **incorrect** code for this rule:

```js

export default {
  head: {
    title: "My page"
  }
}

```

Examples of **correct** code for this rule:

```js

export default {
  head() {
    return {
      title: "My page"
    }
  }
}

```

## Further Reading

* [GitHub - nuxt/require-func-head](https://github.com/nuxt/eslint-plugin-nuxt/blob/master/docs/rules/require-func-head.md)