Pattern: Unknown type selector

Issue: -

## Description

Disallow unknown type selectors. This rule considers tags defined in the `HTML`, `SVG`, and `MathML` specifications to be known.

## Examples

The following patterns are considered violations:

```css
    unknown {}
/** ↑
 * This type selector */
```

```css
tag {}
```

The following patterns are *not* considered violations:

```css
input {}
```

```css
ul li {}
```

```css
li > a {}
```

# Configuration

### `ignore: ["custom-elements", "default-namespace"]`

#### `"custom-elements"`

Allow custom elements.

The following patterns are considered violations:

```css
unknown {}
```

```css
x-Foo {}
```

The following patterns are *not* considered violations:

```css
x-foo {}
```

#### `"default-namespace"`

Allow unknown type selectors if they belong to the default namespace.

The following patterns are considered violations:

```css
namespace|unknown {}
```

The following patterns are *not* considered violations:

```css
unknown {}
```

### `ignoreNamespaces: ["/regex/", "string"]`

Given:

```js
["/^some-/", "custom-namespace"]
```

The following patterns are *not* considered violations:

```css
custom-namespace|unknown {}
```

```css
some-namespace|unknown {}
```

```css
some-other-namespace|unknown {}
```

### `ignoreTypes: ["/regex/", "string"]`

Given:

```js
["/^some-/", "custom-type"]
```

The following patterns are *not* considered violations:

```css
custom-type {}
```

```css
some-type {}
```

```css
some-other-type {}
```

## Further Reading

* [stylelint - selector-type-no-unknown](https://stylelint.io/user-guide/rules/selector-type-no-unknown)