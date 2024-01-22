Pattern: Trailing whitespace

Issue: -

## Description

Adding trailing whitespace can cause extra work for others editing the same file, when they merge, as can removing existing trailing whitespace. So: Don't introduce trailing whitespace. Remove it if you're already changing that line, or do it in a separate clean-up operation (preferably when no-one else is working on the file).

## Examples

The following patterns are considered violations:

```css
a { color: pink; }···
/**               ↑
 *  This whitespace */
```

```css
a { color: pink; }·
```

Comment strings are also checked -- so the following is a violation:

```css
/* something····
 * something else */
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
/* something
 * something else */
```

# Configuration

### `ignore: ["empty-lines"]`

#### `"empty-lines"`

Allow end-of-line whitespace for lines that are only whitespace, "empty" lines.

The following patterns are *not* considered violations:

```css
a {
  color: pink;
··
  background: orange;
}
```

```css
····
```

```css
a { color: pink; }
····
```

## Further Reading

* [stylelint - no-eol-whitespace](https://github.com/stylelint-stylistic/stylelint-stylistic/tree/main/lib/rules/no-eol-whitespace)