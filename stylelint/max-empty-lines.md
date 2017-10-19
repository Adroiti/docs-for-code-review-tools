Pattern: Too many empty lines

Issue: -

## Description

Limit the number of adjacent empty lines.

## Examples

`int`: Maximum number of characters allowed.

For example, with `2`:

The following patterns are considered violations:

```css
a {}



b {}
```

Comment strings are also checked -- so the following is a violation:

```css
/**
 * Call me Ishmael.
 *
 *
 *
 * Some years ago -- never mind how log precisely -- ...
 */
```

The following patterns are *not* considered violations:

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

# Configuration

### `ignore: ["comments"]`

Only enforce the adjacent empty lines limit for lines that are not comments.

For example, with `2` adjacent empty lines:

The following patterns are considered violations:

```css
/* horse */
a {}



b {}
```

The following patterns are *not* considered violations:

```css
/**
 * Call me Ishmael.
 *
 *
 *
 * Some years ago -- never mind how log precisely -- ...
 */
```

```css
a { 
    /**
    * Comment 
    *
    *
    *
    * inside the declaration with a lot of empty lines...
    */
     color: pink; 
}
```

## Further Reading

* [stylelint - max-empty-lines](https://stylelint.io/user-guide/rules/max-empty-lines)