Pattern: Use of offset in plural rule

Issue: -

## Description

Offset has complicated logic implication so some translation vendors don't allow it.

```json
import {defineMessages} from 'react-intl'

const messages = defineMessages({
  // PASS
  foo: {
    defaultMessage: '{var, plural, one{one} other{other}}',
  },
  // FAILS
  bar: {
    defaultMessage: '{var, plural, offset:1 one{one} other{other}}',
  },
})
```

## Further Reading

* [formatjs - no-offset](https://formatjs.io/docs/tooling/linter/#no-offset)