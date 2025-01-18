Pattern: Parameter property declaration in constructor

Issue: -

## Description

⚠️ This rule is deprecated. Use `parameter-properties` instead.

Constructor parameter properties provide a shorthand way to both declare and initialize class members, but can make code harder to read by combining multiple concepts into a single statement. Their usage should be consistent across a codebase.

## Examples

Example of **incorrect** code:
```ts
class User {
  constructor(private name: string, public age: number) {}
}

class Service {
  constructor(
    private readonly config: Config,
    protected logger: Logger,
  ) {}
}
```

Example of **correct** code:
```ts
class User {
  private name: string;
  public age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}

class Service {
  private readonly config: Config;
  protected logger: Logger;

  constructor(config: Config, logger: Logger) {
    this.config = config;
    this.logger = logger;
  }
}
```