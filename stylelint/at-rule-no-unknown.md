Pattern: Unknown at-rule

Issue: -

## Description

Disallow unknown at-rules. This rule considers at-rules defined in the CSS Specifications, up to and including Editor's Drafts, to be known.

## Examples

The following patterns are considered violations:

```css
    @unknown (max-width: 960px) {}
/** ↑
 * At-rules like this */
```

```css
@unknown {}
```

The following patterns are *not* considered violations:

```css
@charset "UTF-8";
```

```css
@CHARSET "UTF-8";
```

```css
@media (max-width: 960px) {}
```

```css
@font-feature-values Font One {
  @styleset {}
}
```

# Configuration

### `ignoreAtRules: ["/regex/", "string"]`

Given:

```js
["/^some-/", "custom"]
```

The following patterns are *not* considered violations:

```css
@some-at-rule "x.css";
```

```css
@some-other-at-rule {}
```

```css
@custom {}
```

## Further Reading

* [stylelint - at-rule-no-unknown](https://stylelint.io/user-guide/rules/at-rule-no-unknown)