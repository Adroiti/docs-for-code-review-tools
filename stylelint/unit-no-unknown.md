Pattern: Unknown unit

Issue: -

## Description

Disallow unknown units. This rule considers units defined in the CSS Specifications, up to and including Editor's Drafts, to be known.

## Examples

The following patterns are considered violations:

```css
a { width: 100pixels; }
/**           ↑
 *  These units */
```

```css
a {
  width: calc(10px + 10pixels);
}
```

The following patterns are *not* considered violations:

```css
a {
  width: 10px;
}  
```

```css
a {
  width: 10Px;
}  
```

```css
a {
  width: 10pX;
}  
```

```css
a {
  width: calc(10px + 10px);
}
```

# Configuration

### `ignoreUnits: ["/regex/", "string"]`

Given:

```js
["/^some-/", "custom"]
```

The following patterns are *not* considered violations:

```css
a {
  width: 10custom;
}
```

```css
a {
  width: 10some-unit;
}
```

```css
a {
  width: 10some-other-unit;
}
```

## Further Reading

* [stylelint - unit-no-unknown](https://stylelint.io/user-guide/rules/unit-no-unknown)