Pattern: Inconsistent class literal exposure style

Issue: -

## Description

Classes can expose literal values either through readonly fields or getter methods. Using both styles within the same codebase reduces readability and maintainability. When targeting JavaScript users, getter methods provide better runtime safety since readonly modifiers are removed during compilation.

## Examples

Example of **incorrect** code when preferring fields:
```ts
class Example {
  // Using getter for literal
  public static get count() {
    return 42;
  }

  private get baseUrl() {
    return 'https://api.example.com';
  }
}

class Config {
  static get DEBUG() {
    return true;
  }
}
```

Example of **correct** code when preferring fields:
```ts
class Example {
  // Using readonly field for literal
  public static readonly count = 42;

  private readonly baseUrl = 'https://api.example.com';

  // Getter allowed for non-literal computed value
  public get apiUrl() {
    return `${this.baseUrl}/v1`;
  }
}

class Config {
  static readonly DEBUG = true;
}
```

Example of **incorrect** code when preferring getters:
```ts
class Example {
  // Using readonly field for literal
  readonly count = 42;
  static readonly DEBUG = true;
  private readonly baseUrl = 'https://api.example.com';
}
```

Example of **correct** code when preferring getters:
```ts
class Example {
  // Using getter for literal
  get count() { return 42; }
  static get DEBUG() { return true; }
  private get baseUrl() { return 'https://api.example.com'; }

  // Regular field for non-literal
  readonly config = { timeout: 1000 };
}
```