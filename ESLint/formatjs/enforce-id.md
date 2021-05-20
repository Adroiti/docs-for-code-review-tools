Pattern: Missing generated ID in `MessageDescriptor`

Issue: -

## Description

Pipelines can enforce automatic/manual ID generation at the linter level (autofix to insert autogen ID) so this guarantees that.

```json
import {defineMessages} from 'react-intl';

const messages = defineMessages({
  // PASS
  foo: {
    id: '19shaf'
    defaultMessage: '{var, plural, one{one} other{other}}',
  },
  // FAILS
  bar: {
    id: 'something',
    defaultMessage: '{var, plural, offset:1 one{one} other{other}}',
  },
  // FAILS
  bar: {
    defaultMessage: '{var, plural, offset:1 one{one} other{other}}',
  },
});
```

## Further Reading

* [formatjs - enforce-id](https://formatjs.io/docs/tooling/linter/#enforce-id)