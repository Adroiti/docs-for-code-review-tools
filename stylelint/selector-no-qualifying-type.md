Pattern: Qualifying a selector by type

Issue: -

## Description

Disallow qualifying a selector by type. A type selector is "qualifying" when it is compounded with (chained to) another selector (e.g. a.foo, a#foo). This rule does not regulate type selectors that are combined with other selectors via a combinator (e.g. a > .foo, a #foo).

## Examples

The following patterns are considered violations:

```css
    a.foo {}
/** ↑
 * This type selector is qualifying the class */
```

```css
a#foo {
  margin: 0
}
```

```css
input[type='button'] {
  margin: 0
}
```

The following patterns are *not* considered violations:

```css
.foo {
  margin: 0
}
```

```css
#foo {
  margin: 0
}
```

```css
input {
  margin: 0
}
```

# Configuration

### `ignore: ["attribute", "class", "id"]`

#### `"attribute"`

Allow attribute selectors qualified by type.

The following patterns are *not* considered violations:

```css
input[type='button'] {
  margin: 0
}
```

#### `"class"`

Allow class selectors qualified by type.

The following patterns are *not* considered violations:

```css
a.foo {
  margin: 0
}
```

#### `"id"`

Allow id selectors qualified by type.

The following patterns are *not* considered violations:

```css
a#foo {
  margin: 0
}
```

## Further Reading

* [stylelint - selector-no-qualifying-type](https://stylelint.io/user-guide/rules/selector-no-qualifying-type)