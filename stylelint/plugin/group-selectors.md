Pattern: Ungrouped selectors

Issue: -

## Description

Identify the selectors, which can be grouped, as they have same set of properties and values.

```css
  .a{ display: inline-block;width: 100px;}
  .b{display:inline-block;width:100px;}
```

Above selectors can be grouped like this:

```css
.a,.b{display:inline-block;width: 100px;}
```

## Further Reading

* [stylelint-group-selectors](https://github.com/ssivanatarajan/stylelint-group-selectors)