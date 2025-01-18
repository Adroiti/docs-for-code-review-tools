Pattern: Direct value comparison with enum

Issue: -

## Description

Comparing enum values with non-enum values undermines the purpose of enums and makes code less maintainable. Comparing against literal values instead of enum members makes code less resilient to enum value changes and prevents tooling features like "Rename Symbol" from working correctly.

## Examples

Example of **incorrect** code:
```ts
enum Fruit {
  Apple,
}

declare let fruit: Fruit;
// Comparison with literal instead of enum member
fruit === 0;

enum Vegetable {
  Asparagus = 'asparagus',
}

declare let vegetable: Vegetable;
// Comparison with string instead of enum member
vegetable === 'asparagus';

declare let anyString: string;
// Comparison between enum and non-enum value
anyString === Vegetable.Asparagus;
```

Example of **correct** code:
```ts
enum Fruit {
  Apple,
}

declare let fruit: Fruit;
fruit === Fruit.Apple;

enum Vegetable {
  Asparagus = 'asparagus',
}

declare let vegetable: Vegetable;
vegetable === Vegetable.Asparagus;
```