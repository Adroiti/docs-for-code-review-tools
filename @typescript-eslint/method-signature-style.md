Pattern: Inconsistent method signature format

Issue: -

## Description

TypeScript allows two ways to define a method signature in an interface or type: method shorthand (`method(arg: string): void`) and property function type (`method: (arg: string) => void`). Mixing these styles reduces readability and affects type checking behavior, as method signatures use different variance rules than function properties in strict mode.

## Examples

Example of **incorrect** code when preferring property style:
```ts
interface Example {
  func(arg: string): number;
  
  other(arg: boolean): void;
  
  multi(arg: number): void;
  multi(arg: string): void;
}

type Shape = {
  draw(x: number): void;
  paint(color: string): void;
}
```

Example of **correct** code when preferring property style:
```ts
interface Example {
  func: (arg: string) => number;
  
  other: (arg: boolean) => void;
  
  // Multiple signatures combined with intersection type
  multi: ((arg: number) => void) & ((arg: string) => void);
}

type Shape = {
  draw: (x: number) => void;
  paint: (color: string) => void;
}
```

Example of **incorrect** code when preferring method style:
```ts
interface Example {
  func: (arg: string) => number;
  
  other: (arg: boolean) => void;
}

type Shape = {
  draw: (x: number) => void;
  paint: (color: string) => void;
}
```

Example of **correct** code when preferring method style:
```ts
interface Example {
  func(arg: string): number;
  
  other(arg: boolean): void;
}

type Shape = {
  draw(x: number): void;
  paint(color: string): void;
}
```