Pattern: Duplicate `@import`

Issue: -

## Description

Disallows duplicate `@import` rules within a stylesheet.

## Examples

The following patterns are considered violations:

```css
@import 'a.css';
@import 'a.css';
```

```css
@import url("a.css");
@import url("a.css");
```

```css
@import "a.css";
@import 'a.css';
```

```css
@import "a.css";
@import 'b.css';
@import url(a.css);
```

The following patterns are *not* considered violations:

```css
@import "a.css";
@import "b.css";
```

```css
@import url('a.css') projection;
@import url('a.css') tv;
```

## Further Reading

* [stylelint - no-duplicate-at-import-rules](https://stylelint.io/user-guide/rules/no-duplicate-at-import-rules)