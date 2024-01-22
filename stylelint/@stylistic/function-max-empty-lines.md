Pattern: Too many empty lines in function

Issue: -

## Description

Limit the number of adjacent empty lines within functions.

## Examples

`int`: Maximum number of characters allowed.

For example, with `0`:

The following patterns are considered violations:

```css
a {
  transform:
    translate(

      1,
      1
    );
}
```

```css
a {
  transform:
    translate(
      1,

      1
    );
}
```

```css
a {
  transform:
    translate(
      1,
      1

    );
}
```

The following patterns are *not* considered violations:

```css
a {
  transform: 
    translate(
      1, 
      1
    );
}
```

## Further Reading

* [stylelint - function-max-empty-lines](https://github.com/stylelint-stylistic/stylelint-stylistic/tree/main/lib/rules/function-max-empty-lines)