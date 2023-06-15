Pattern: Malformed trailing `;` in declaration block

Issue: -

## Description

Require or disallow a trailing semicolon within declaration blocks. The trailing semicolon is the *last* semicolon in a declaration block and it is optional.

This rule will ignore Less mixins, trailing `//` comments, and declaration blocks containing nested (at-)rules.

## Examples

### `"always"`

There *must always* be a trailing semicolon.

The following patterns are considered violations:

```css
a { color: pink }
```

```css
a { background: orange; color: pink }
```

```css
a { @include foo }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a { background: orange; color: pink; }
```

```css
a { @include foo; }
```

### `"never"`

There *must never* be a trailing semicolon.

The following patterns are considered violations:

```css
a { color: pink; }
```

```css
a { background: orange; color: pink; }
```

The following patterns are *not* considered violations:

```css
a { color: pink }
```

```css
a { background: orange; color: pink }
```

## Further Reading

* [stylelint - declaration-block-trailing-semicolon](https://stylelint.io/user-guide/rules/declaration-block-trailing-semicolon)