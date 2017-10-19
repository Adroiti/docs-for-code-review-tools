Pattern: Empty source file

Issue: -

## Description

A source containing only whitespace is considered empty.

## Examples

The following patterns are considered violations:

```css

```

```css
\t\t
```

```css
\n
```

The following patterns are *not* considered violations:

```css
a {}
```

```css
/* Only comments */
```

## Further Reading

* [stylelint - no-empty-source](https://stylelint.io/user-guide/rules/no-empty-source)