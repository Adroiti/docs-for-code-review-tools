Pattern: Incorrect spacing after bang

Issue: -

## Description

Require a single space or disallow whitespace after the bang of declarations.

```css
a { color: pink !important; }
/**             ↑
 * The space after this exclamation mark */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There _must always_ be a single space after the bang.

The following patterns are considered problems:

```css
a { color: pink !important; }
```

```css
a { color: pink      !important; }
```

The following patterns are _not_ considered problems:

```css
a { color: pink ! important; }
```

```css
a { color: pink! important; }
```

### `"never"`

There _must never_ be whitespace after the bang.

The following patterns are considered problems:

```css
a { color: pink ! important; }
```

```css
a { color: pink! important; }
```

The following patterns are _not_ considered problems:

```css
a { color: pink !important; }
```

```css
a { color:pink!important; }
```

## Further Reading

* [stylelint - declaration-bang-space-after](https://stylelint.io/user-guide/rules/declaration-bang-space-after)