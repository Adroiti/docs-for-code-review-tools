Pattern: Implicit enum member value

Issue: -

## Description

Enum members without explicit values rely on TypeScript's automatic sequential numbering, which can lead to bugs if enum members are reordered or new members are added. Each enum member should have an explicit value to ensure values remain stable over time.

## Examples

Example of **incorrect** code:
```ts
enum Status {
  Open = 1,
  Close,  // Implicitly 2
}

enum Direction {
  Up,    // Implicitly 0
  Down,  // Implicitly 1
}

enum Color {
  Red,              // Implicitly 0
  Green = 'Green',
  Blue = 'Blue',
}
```

Example of **correct** code:
```ts
enum Status {
  Open = 'Open',
  Close = 'Close',
}

enum Direction {
  Up = 1,
  Down = 2,
}

enum Color {
  Red = 'Red',
  Green = 'Green',
  Blue = 'Blue',
}
```