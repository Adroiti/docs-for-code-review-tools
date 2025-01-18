⚠️ This rule is deprecated. Use [`import/no-duplicates`](https://github.com/import-js/eslint-plugin-import/blob/HEAD/docs/rules/no-duplicates.md) instead.

Pattern: Duplicate import from same module

Issue: -

## Description

Multiple import statements from the same module can make code harder to maintain and may impact performance. All imports from a module should be consolidated into a single import statement.

## Examples

Example of **incorrect** code:
```ts
import { foo } from 'module';
import { bar } from 'module';

import type { Type1 } from 'module';
import type { Type2 } from 'module';
```

Example of **correct** code:
```ts
import { foo, bar } from 'module';

import type { Type1, Type2 } from 'module';
```