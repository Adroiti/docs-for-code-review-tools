Pattern: Use of multiple whitespaces

Issue: -

## Description

Consecutive whitespaces are handled differently in different locales. It also prevents `\` linebreaks in JS string which results in awkward whitespaces.

```json
import {defineMessages} from 'react-intl'

const messages = defineMessages({
  // WORKS
  foo: {
    defaultMessage: 'Smileys & People',
  },
  // FAILS
  bar: {
    defaultMessage: 'Smileys &   People',
  },
  // FAILS
  baz: {
    defaultMessage: 'this message is too long \
    so I wanna line break it.',
  },
})
```

## Further Reading

* [formatjs - no-multiple-whitespaces](https://formatjs.io/docs/tooling/linter/#no-multiple-whitespaces)