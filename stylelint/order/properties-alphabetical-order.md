Pattern: Wrong property alphabetical order in declaration block

Issue: -

## Description

Specify the alphabetical order of properties within declaration blocks. Prefixed properties *must always* precede the unprefixed version.

This rule ignores variables (`$sass`, `@less`, `--custom-property`).

## Examples

The following patterns are considered warnings:

```css
a {
	top: 0;
	color: pink;
}
```

```css
a {
	-moz-transform: scale(1);
	transform: scale(1);
	-webkit-transform: scale(1);
}
```

The following patterns are *not* considered warnings:

```css
a {
	color: pink;
	top: 0;
}
```

```css
a {
	-webkit-transform: scale(1);
	-moz-transform: scale(1);
	transform: scale(1);
}
```

```css
a {
	-moz-transform: scale(1);
	-webkit-transform: scale(1);
	transform: scale(1);
}
```

## Further Reading

* [stylelint-order - properties-alphabetical-order](https://github.com/hudochenkov/stylelint-order/blob/master/rules/properties-alphabetical-order/README.md)
