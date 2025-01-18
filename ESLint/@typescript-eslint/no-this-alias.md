Pattern: Alias of this keyword

Issue: -

## Description

Using a variable alias for `this` often indicates outdated pre-ES6 practices or poor scope management. Arrow functions automatically bind `this` correctly, making aliases unnecessary.

## Examples

Example of **incorrect** code:
```ts
const self = this;

setTimeout(function () {
  self.doWork();
});
```

Example of **correct** code:
```ts
setTimeout(() => {
  this.doWork();
});
```