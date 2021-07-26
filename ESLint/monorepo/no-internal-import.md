Pattern: Use of internal import

Issue: -

## Description

Forbids importing specific files from a monorepo package.

## Examples

```js
// Bad
import 'module/src/foo.js';

// Good
import { foo } from 'module';
```

## Further Reading

* [GitHub - monorepo/no-internal-import](https://github.com/azz/eslint-plugin-monorepo#monorepono-internal-import)