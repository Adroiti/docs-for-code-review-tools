Pattern: Unknown custom property

Issue: -

## Description

Disallows usage of unknown custom properties.

## Examples

### true

If the first option is `true`, the rule requires all custom properties to be known, and the following patterns are
_not_ considered violations:

```css
:root {
  --brand-blue: #33f;
}

.example {
  color: var(--brand-blue);
}
```

```css
.example {
  color: var(--brand-blue);
}

.some-other-class {
  --brand-blue: #33f;
}
```

```css
:root {
  --brand-blue: #33f;
  --brand-color: var(--brand-blue);
}
```

While the following patterns are considered violations:

```css
.example {
  color: var(--brand-blue);
}
```

```css
:root {
  --brand-color: var(--brand-blue);
}
```

## Further Reading

* [stylelint-value-no-unknown-custom-properties](https://github.com/csstools/stylelint-value-no-unknown-custom-properties)