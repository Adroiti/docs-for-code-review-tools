Pattern: Too many consecutive empty lines

Issue: -

## Description

Limit the number of adjacent empty lines.

```css
a {}
     /* ← */
     /* ← */
a {} /* ↑ */
/**     ↑
 * These lines */
```

## Examples

`int`: Maximum number of adjacent empty lines allowed.

For example, with `2`:

The following patterns are considered problems:

```css
a {}

b {}
```

Comment strings are also checked -- so the following is a problem:

```css
/*
 Call me Ishmael.

 Some years ago--never mind how long precisely-—...
 */
```

The following patterns are _not_ considered problems:

```css
a {}
b {}
```

```css
a {}

b {}
```

```css
a {}


b {}
```

## Configuration

### `ignore: ["comments"]`

Only enforce the adjacent empty lines limit for lines that are not comments.

For example, with `2` adjacent empty lines:

The following patterns are considered problems:

```css
/* horse */
a {}

b {}
```

The following patterns are _not_ considered problems:

```css
/*
 Call me Ishmael.

 Some years ago -- never mind how long precisely -- ...
 */
```

```css
a {
    /*
     Comment


     inside the declaration with a lot of empty lines...
    */
     color: pink;
}
```

## Further Reading

* [stylelint - max-empty-lines](https://stylelint.io/user-guide/rules/max-empty-lines)