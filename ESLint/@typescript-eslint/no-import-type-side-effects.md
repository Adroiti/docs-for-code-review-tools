Pattern: Unnecessary side-effect import from inline type qualifier

Issue: -

## Description

When using inline type qualifiers in imports, TypeScript may generate unnecessary side-effect imports when transpiling. This happens when all imported members have inline type qualifiers but the import statement lacks a top-level type modifier, causing an empty import to remain in the output code.

## Examples

Example of **incorrect** code:
```ts
// Creates empty import in output
import { type A } from 'module';

// Creates side-effect import
import { type User, type Settings } from './types';

// Multiple renamed imports still create side-effect
import { type A as UserA, type B as UserB } from 'users';

// Mixed type imports without top-level qualifier
import { type Config, type Options } from './config';
```

Example of **correct** code:
```ts
// Proper type-only import
import type { A } from 'module';

// Multiple type imports with top-level qualifier
import type { User, Settings } from './types';

// Renamed imports with top-level qualifier
import type { A as UserA, B as UserB } from 'users';

// Mixed value and type imports
import { value, type Type } from 'module';

// Namespace imports
import type * as Types from './types';

// Direct type imports
import type Config from './config';

// Side-effect import when actually needed
import 'module-with-side-effects';
```