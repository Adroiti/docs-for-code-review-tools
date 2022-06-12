Pattern: Missing notation for `@import`

Issue: -

## Description

Specify string or URL notation for `@import` rules.

## Examples

`string`: `"string"|"url"`

### `"string"`

`@import` rules _must always_ use string notation.

The following patterns are considered problems:

<!-- prettier-ignore -->
```css
@import url(foo.css);
```

<!-- prettier-ignore -->
```css
@import url('foo.css');
```

<!-- prettier-ignore -->
```css
@import url("foo.css");
```

The following patterns are _not_ considered problems:

<!-- prettier-ignore -->
```css
@import 'foo.css';
```

<!-- prettier-ignore -->
```css
@import "foo.css";
```

### `"url"`

`@import` rules _must always_ use URL notation.

The following patterns are considered problems:

<!-- prettier-ignore -->
```css
@import 'foo.css';
```

<!-- prettier-ignore -->
```css
@import "foo.css";
```

The following patterns are _not_ considered problems:

<!-- prettier-ignore -->
```css
@import url(foo.css);
```

<!-- prettier-ignore -->
```css
@import url('foo.css');
```

<!-- prettier-ignore -->
```css
@import url("foo.css");
```

## Further Reading

* [stylelint - import-notation](https://stylelint.io/user-guide/rules/list/import-notation)