Pattern: Import from restricted module

Issue: -

## Description

Some modules in a codebase may be deprecated, have known issues, or be intended only for specific parts of the code. Using imports from these modules can lead to maintenance problems or architectural violations. Both value and type imports can be restricted to enforce these boundaries.

## Examples

Example of **incorrect** code:
```ts
// Direct imports from restricted modules
import oldUtil from 'deprecated-utils';
import { helper } from 'internal-only';

// Namespace imports
import * as legacy from 'legacy-lib';

// Type imports when not allowed
import type { UserType } from 'old-types';

// Re-exports
export { Thing } from 'restricted-module';

// Require-style imports
import dep = require('deprecated-module');

// Mixed type/value imports
import { type OldType, oldFunction } from 'mixed-exports';
```

Example of **correct** code:
```ts
// Using approved alternatives
import { newUtil } from 'new-utils';
import { helper } from 'public-api';

// Type imports when explicitly allowed
import type { UserType } from 'allowed-types';

// Namespace imports from allowed modules
import * as api from 'approved-api';

// Using newer versions
import { Thing } from 'new-module';

// Modern ES imports
import { feature } from 'current-module';

// Separate type imports
import type { NewType } from 'types';
import { newFunction } from 'implementation';
```