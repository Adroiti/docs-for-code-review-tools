Pattern: Duplicate custom property in declaration block

Issue: -

## Description

Disallow duplicate custom properties within declaration blocks.

<!-- prettier-ignore -->
```css
a { --custom-property: pink; --custom-property: orange; }
/** ↑                        ↑
 * These duplicated custom properties */
```

## Examples

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { --custom-property: pink; --custom-property: orange; }
```

<!-- prettier-ignore -->
```css
a { --custom-property: pink; background: orange; --custom-property: orange }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { --custom-property: pink; }
```

<!-- prettier-ignore -->
```css
a { --custom-property: pink; --cUstOm-prOpErtY: orange; }
```

## Further Reading

* [stylelint - declaration-block-no-duplicate-custom-properties](https://stylelint.io/user-guide/rules/declaration-block-no-duplicate-custom-properties)