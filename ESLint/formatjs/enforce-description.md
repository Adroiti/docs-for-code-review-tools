Pattern: Missing description

Issue: -

## Description

Description provides helpful context for translators.

```json
import {defineMessages} from 'react-intl'

const messages = defineMessages({
  // WORKS
  foo: {
    defaultMessage: 'foo',
    description: 'bar',
  },
  // FAILS
  bar: {
    defaultMessage: 'bar',
  },
})
```


## Further Reading

* [formatjs - enforce-description](https://formatjs.io/docs/tooling/linter/#enforce-description)