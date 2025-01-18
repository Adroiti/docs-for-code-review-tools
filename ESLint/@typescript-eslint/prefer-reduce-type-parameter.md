Pattern: Type assertion in Array reduce

Issue: -

## Description

Using type assertions with empty arrays or objects as initial values in `Array#reduce` can lead to subtle type errors. Instead of using `as` assertions, providing the type as a generic type parameter to `reduce` is safer and more explicit.

## Examples

Example of **incorrect** code:
```ts
[1, 2, 3].reduce((arr, num) => arr.concat(num * 2), [] as number[]);

['a', 'b'].reduce(
  (accum, name) => ({
    ...accum,
    [name]: true,
  }),
  {} as Record<string, boolean>
);

const numbers = [1, 2, 3];
numbers.reduce((sum, n) => sum + n, 0 as number);
```

Example of **correct** code:
```ts
[1, 2, 3].reduce<number[]>((arr, num) => arr.concat(num * 2), []);

['a', 'b'].reduce<Record<string, boolean>>(
  (accum, name) => ({
    ...accum,
    [name]: true,
  }),
  {}
);

const numbers = [1, 2, 3];
numbers.reduce<number>((sum, n) => sum + n, 0);
```