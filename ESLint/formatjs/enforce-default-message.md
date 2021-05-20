Pattern: Missing `defaultMessage`

Issue: -

## Description

Can be useful in case you want to extract messages for translations from source code. This way can make sure people won't forget about `defaultMessage`.

```json
import {defineMessages} from 'react-intl'

const messages = defineMessages({
  // WORKS
  foo: {
    defaultMessage: 'This is default message',
    description: 'bar',
  },
  // FAILS
  bar: {
    description: 'bar',
  },
})
```


## Further Reading

* [formatjs - enforce-default-message](https://formatjs.io/docs/tooling/linter/#enforce-default-message)