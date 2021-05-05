Pattern: Use of `require`/`modules.exports`/`exports` in `nuxt.config.js`

Issue: -

## Description

This rule is for preventing using `require`/`modules.exports`/`exports` in `nuxt.config.js`.

Examples of **incorrect** code for this rule:

```js
const { name } = require('./package.json')

module.exports = {
  mode: 'universal',
  name
}
```

Examples of **correct** code for this rule:

```js
import { name } from './package.json'

export default {
  mode: 'universal',
  name
}
```

## Further Reading

* [GitHub - nuxt/no-cjs-in-config](https://github.com/nuxt/eslint-plugin-nuxt/blob/master/docs/rules/no-cjs-in-config.md)