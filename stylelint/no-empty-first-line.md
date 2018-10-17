Pattern: First line is empty

Issue: -

## Description

Disallow empty first lines.

## Examples

The following patterns are considered violations:

```css
    \n
    /** ↑
     * This newline */
    a { color: pink; }
```

```css
\n
a { color: pink; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

## Further Reading

* [stylelint - no-empty-first-line](https://stylelint.io/user-guide/rules/no-empty-first-line)