Pattern: Unexpected missing generic font family

Issue: -

## Description

Disallows missing generic families in lists of font family names.

## Examples

The following patterns are considered violations:

```css
a { font-family: Helvetica, Arial, Verdana, Tahoma; }
```

```css
a { font: 1em/1.3 Times; }
```

The following patterns are *not* considered violations:

```css
a { font-family: Helvetica, Arial, Verdana, Tahoma, sans-serif; }
```

```css
a { font: 1em/1.3 Times, serif; }
```

It's also *not* a violation to use a keyword related to property inheritance.

```css
a { font: inherit; }
b { font: initial; }
i { font: unset; }
```

It's also *not* a violation to use a generic font family anywhere in the list. In other words, the generic font name doesn't need to be the last.

```css
a { font-family: Helvetica Neue, sans-serif, Apple Color Emoji; }
```

## Further Reading

* [stylelint - font-family-no-missing-generic-family-keyword](https://stylelint.io/user-guide/rules/font-family-no-missing-generic-family-keyword)