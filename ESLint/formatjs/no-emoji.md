Pattern: Use of emoji

Issue: -

## Description

Certain translation vendors cannot handle emojis and cross-platform encoding for emojis are faulty.

```json
import {defineMessages} from 'react-intl'

const messages = defineMessages({
  // WORKS
  foo: {
    defaultMessage: 'Smileys & People',
  },
  // FAILS
  bar: {
    defaultMessage: '😃 Smileys & People',
  },
})
```

## Further Reading

* [formatjs - no-emoji](https://formatjs.io/docs/tooling/linter/#no-emoji)