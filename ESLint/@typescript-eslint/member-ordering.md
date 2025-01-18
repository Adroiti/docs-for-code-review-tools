Pattern: Inconsistent member order in class or interface

Issue: -

## Description

When class and interface members (properties, methods, constructors) lack a consistent ordering scheme, code becomes harder to read and maintain. Members should be grouped and ordered following a consistent pattern, such as by member type, visibility (public/private), or alphabetically.

## Examples

Example of **incorrect** code:
```ts
class Example {
  private instanceField: string;
  static staticMethod(): void {}
  constructor() {}
  public method(): void {}
  private static staticField = 1;
  static {} // static initialization
}

interface BadInterface {
  field: string;
  new(): BadInterface;
  method(): void;
  [key: string]: any;
}

type BadType = {
  c: number;
  a(): void;
  b: string;
}
```

Example of **correct** code with standard grouping:
```ts
class Example {
  // Static members first
  private static staticField = 1;
  static staticMethod(): void {}
  static {} // static initialization
  
  // Instance fields
  private instanceField: string;
  
  // Constructor
  constructor() {}
  
  // Instance methods
  public method(): void {}
}

interface GoodInterface {
  // Index signature
  [key: string]: any;
  
  // Fields
  field: string;
  
  // Methods
  method(): void;
  
  // Constructor signature
  new(): GoodInterface;
}

type GoodType = {
  // Fields first
  b: string;
  c: number;
  
  // Methods last
  a(): void;
}
```

Example of **correct** code with alphabetical ordering:
```ts
class Example {
  constructor() {}
  instanceField: string;
  method(): void {}
  otherMethod(): void {}
  static staticField = 1;
  static staticMethod(): void {}
}
```