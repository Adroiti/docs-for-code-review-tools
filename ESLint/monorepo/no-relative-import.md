Pattern: Use of relative import

Issue: -

## Description

Forbids importing other packages from the monorepo with a relative path.

## Examples

```js
// Bad
import module from '../module';

// Good
import module from 'module';
```

## Further Reading

* [GitHub - monorepo/no-relative-import](https://github.com/azz/eslint-plugin-monorepo#monorepono-relative-import-fixable)