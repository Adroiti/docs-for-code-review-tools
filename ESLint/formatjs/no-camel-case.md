Pattern: Use of camel-case

Issue: -

## Description

This is to prevent case-sensitivity issue in certain translation vendors.

```json
import {defineMessages} from 'react-intl'

const messages = defineMessages({
  // WORKS
  foo: {
    defaultMessage: 'foo {snake_case} {nothing}',
  },
  // FAILS
  bar: {
    defaultMessage: 'foo {camelCase}',
  },
})
```

## Further Reading

* [formatjs - no-camel-case](https://formatjs.io/docs/tooling/linter/#no-camel-case)