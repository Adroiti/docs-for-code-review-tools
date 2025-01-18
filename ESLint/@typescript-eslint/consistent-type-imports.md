Pattern: Missing type modifier in import statement

Issue: -

## Description

TypeScript allows marking imports with the type modifier to indicate they exist only in the type system. When type imports are mixed with regular imports, transpilers cannot safely remove type-only imports, potentially leading to larger bundle sizes and runtime errors.

## Examples

Example of **incorrect** code:
```ts
// Regular imports used for types
import { UserType } from './types';
import { Theme } from './theme';

type Props = {
  user: UserType;
  theme: Theme;
};

// Mixed imports without type modifier
import { Button, ButtonProps } from './components';
import Card, { CardProps } from './card';

// Type reference using regular import
const form: FormData = new FormData();
```

Example of **correct** code:
```ts
// Using type imports for type references
import type { UserType } from './types';
import type { Theme } from './theme';

type Props = {
  user: UserType;
  theme: Theme;
};

// Separate type and value imports
import { Button } from './components';
import type { ButtonProps } from './components';

// Inline type modifier syntax (TS 4.5+)
import { type CardProps, Card } from './card';

// Regular import for value usage
import { FormData } from './forms';
const form = new FormData();
```