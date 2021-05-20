Pattern: Use of multiple plurals

Issue: -

## Description

Nested plurals are hard to translate across languages so some translation vendors don't allow it.

```json
import {defineMessages} from 'react-intl'

const messages = defineMessages({
    // WORKS
    foo: {
        defaultMessage: '{p1, plural, one{one}}',
    },
    // FAILS
    bar: {
        defaultMessage: '{p1, plural, one{one}} {p2, plural, one{two}}',
    }
    // ALSO FAILS
    bar2: {
        defaultMessage: '{p1, plural, one{{p2, plural, one{two}}}}',
    }
})
```

## Further Reading

* [formatjs - no-multiple-plurals](https://formatjs.io/docs/tooling/linter/#no-multiple-plurals)