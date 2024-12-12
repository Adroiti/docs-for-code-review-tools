Pattern: Incorrect spacing before attribute selector operator

Issue: -

## Description

Require a single space or disallow whitespace before operators within attribute selectors.

```css
[target =_blank]
/**     ↑
 * The space before operator */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There _must always_ be a single space before the operator.

The following patterns are considered problems:

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

The following patterns are _not_ considered problems:

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

There _must never_ be a single space before the operator.

The following patterns are considered problems:

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

The following patterns are _not_ considered problems:

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