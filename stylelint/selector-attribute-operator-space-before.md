Pattern: Malformed whitespace before operator in attribute selector

Issue: -

## Description

Require a single space or disallow whitespace before operators within attribute selectors.

## Examples

### `"always"`

There *must always* be a single space before the operator.

The following patterns are considered violations:

```css
[target=_blank] {}
```

```css
[target= _blank] {}
```

```css
[target='_blank'] {}
```

```css
[target="_blank"] {}
```

```css
[target= '_blank'] {}
```

```css
[target= "_blank"] {}
```

The following patterns are *not* considered violations:

```css
[target] {}
```

```css
[target =_blank] {}
```

```css
[target ='_blank'] {}
```

```css
[target ="_blank"] {}
```

```css
[target = _blank] {}
```

```css
[target = '_blank'] {}
```

```css
[target = "_blank"] {}
```

### `"never"`

There *must never* be a single space before the operator.

The following patterns are considered violations:

```css
[target =_blank] {}
```

```css
[target = _blank] {}
```

```css
[target ='_blank'] {}
```

```css
[target ="_blank"] {}
```

```css
[target = '_blank'] {}
```

```css
[target = "_blank"] {}
```

The following patterns are *not* considered violations:

```css
[target] {}
```

```css
[target=_blank] {}
```

```css
[target='_blank'] {}
```

```css
[target="_blank"] {}
```

```css
[target= _blank] {}
```

```css
[target= '_blank'] {}
```

```css
[target= "_blank"] {}
```

## Further Reading

* [stylelint - selector-attribute-operator-space-before](https://stylelint.io/user-guide/rules/selector-attribute-operator-space-before)