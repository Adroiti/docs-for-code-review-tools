Pattern: Malformed quotes for attribute value

Issue: -

## Description

Require or disallow quotes for attribute values.

## Examples

### `"always"`

Attribute values *must always* be quoted.

The following patterns are considered violations:

```css
[title=flower] {}
```

```css
[class^=top] {}
```

The following patterns are *not* considered violations:

```css
[title] {}
```

```css
[target="_blank"] {}
```

```css
[class|="top"] {}
```

```css
[title~='text'] {}
```

```css
[data-attribute='component'] {}
```

### `"never"`

Attribute values *must never* be quoted.

The following patterns are considered violations:

```css
[target="_blank"] {}
```

```css
[class|="top"] {}
```

```css
[title~='text'] {}
```

```css
[data-attribute='component'] {}
```

The following patterns are *not* considered violations:

```css
[title] {}
```

```css
[title=flower] {}
```

```css
[class^=top] {}
```

## Further Reading

* [stylelint - selector-attribute-quotes](https://stylelint.io/user-guide/rules/selector-attribute-quotes)