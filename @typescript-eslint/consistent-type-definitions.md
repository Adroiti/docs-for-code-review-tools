Pattern: Mixed interface and type definition syntax

Issue: -

## Description

TypeScript provides two ways to define object types: using interface declarations (`interface`) or type aliases (`type`). While they are often interchangeable, mixing both styles in a codebase reduces readability and makes it harder to maintain consistent patterns.

## Examples

Example of **incorrect** code when preferring interface:
```ts
// Using type for object shape
type User = {
  name: string;
  age: number;
};

// Mixing styles in related types
interface Animal {
  species: string;
}
type Pet = {
  name: string;
  breed: string;
};
```

Example of **correct** code when preferring interface:
```ts
// Using interface for object shapes
interface User {
  name: string;
  age: number;
}

interface Animal {
  species: string;
}

interface Pet {
  name: string;
  breed: string;
}

// Type aliases still used for non-object types
type ID = string | number;
type Handler = (event: Event) => void;
type Status = 'active' | 'inactive';
```

Example of **correct** code when preferring type:
```ts
// Using type consistently
type User = {
  name: string;
  age: number;
};

type Animal = {
  species: string;
};

type Pet = {
  name: string;
  breed: string;
};
```