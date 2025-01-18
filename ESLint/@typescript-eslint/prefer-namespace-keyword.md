Pattern: Module keyword instead of namespace

Issue: -

## Description

The `module` keyword for code organization in TypeScript has been replaced by the `namespace` keyword. While both still work for defining custom modules, using `module` is outdated and may lead to confusion. The `module` keyword should only be used for external module declarations.

## Examples

Example of **incorrect** code:
```ts
module Example {
  export interface Person {
    name: string;
  }
}

module Utils {
  export function helper() {
    return true;
  }
}
```

Example of **correct** code:
```ts
namespace Example {
  export interface Person {
    name: string;
  }
}

namespace Utils {
  export function helper() {
    return true;
  }
}

// Module keyword is fine for external declarations
declare module 'foo' {
  export function bar(): void;
}
```