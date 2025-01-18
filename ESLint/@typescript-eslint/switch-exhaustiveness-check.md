Pattern: Non-exhaustive switch statement

Issue: -

## Description

A switch statement that doesn't handle all possible values of a union type or enum can lead to runtime errors when new values are added. When a union type or enum changes, existing switch statements need to be updated to handle any new values, but TypeScript won't highlight missing cases unless exhaustiveness checking is enforced.

## Examples

Example of **incorrect** code:
```ts
type Color = 'red' | 'green' | 'blue';
declare const color: Color;

switch (color) {
  case 'red':
    handleRed();
    break;
  case 'blue':
    handleBlue();
    break;
  // Missing 'green' case!
}

enum Direction {
  Up,
  Down,
  Left,
  Right,
}
declare const dir: Direction;

switch (dir) {
  case Direction.Up:
    moveUp();
    break;
  case Direction.Down:
    moveDown();
    break;
  // Missing Left and Right cases!
}
```

Example of **correct** code:
```ts
type Color = 'red' | 'green' | 'blue';
declare const color: Color;

switch (color) {
  case 'red':
    handleRed();
    break;
  case 'green':
    handleGreen();
    break;
  case 'blue':
    handleBlue();
    break;
}

// Alternative with default case (if allowed)
switch (color) {
  case 'red':
    handleRed();
    break;
  default:
    handleOthers();
    break;
}
```