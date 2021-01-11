Pattern: Use of disallowed attribute name

Issue: -

## Description

Specify a list of disallowed attribute names.

<!-- prettier-ignore -->
```css
    [class~="foo"] {}
/**  ↑
 * This name */
```

## Examples

The following patterns are considered violations:

```css
[class*="foo"] {}
```

```css
[id~="bar"] {}
```

```css
[data-foo*="bar"] {}
```

The following patterns are _not_ considered violations:

```css
[lang~="en-us"] {}
```

```css
[target="_blank"] {}
```

```css
[href$=".bar"] {}
```

## Further Reading

* [stylelint - selector-attribute-name-disallowed-list](https://stylelint.io/user-guide/rules/selector-attribute-name-disallowed-list)