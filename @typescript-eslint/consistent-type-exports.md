Pattern: Missing type modifier in export statement

Issue: -

## Description

TypeScript allows marking exports with the type modifier to indicate they exist only in the type system. When type exports are mixed with regular exports, transpilers cannot safely remove type-only exports, potentially leading to larger bundle sizes and runtime errors.

## Examples

Example of **incorrect** code:
```ts
// Mixing type and value exports without type modifier
interface ButtonProps {
  onClick: () => void;
}

class Button implements ButtonProps {
  onClick = () => console.log('clicked');
}

export { Button, ButtonProps };

// Multiple exports mixing types and values
const x = 1;
type T = number;
export { x, T };

// Exporting type with value syntax
interface Config {}
export { Config };
```

Example of **correct** code:
```ts
// Separate type and value exports
interface ButtonProps {
  onClick: () => void;
}

class Button implements ButtonProps {
  onClick = () => console.log('clicked');
}

export { Button };
export type { ButtonProps };

// Using inline type modifier (TS 4.5+)
const x = 1;
type T = number;
export { x, type T };

// Multiple type-only exports
interface Config {}
type Options = {};
export type { Config, Options };
```