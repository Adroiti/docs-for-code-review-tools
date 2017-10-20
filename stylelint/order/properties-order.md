Pattern: Wrong property order in declaration block

Issue: -

## Description

Specify the order of properties within declaration blocks.

Within an order array, you can include

* unprefixed property names
* group objects with these properties:
	* `order: "flexible"`: If property isn't set (the default), the properties in this group must come in the order specified. If `"flexible"`, the properties can be in any order as long as they are grouped correctly.
	* `properties (array of strings)`: The properties in this group.
	* `emptyLineBefore ("always"|"never")`: If `always`, this group must be separated from other properties by an empty newline. If emptyLineBefore is `never`, the group must have no empty lines separating it from other properties. By default this property isn't set. Rule will check empty lines between properties _only_. However, shared-line comments ignored by rule. Shared-line comment is a comment on the same line as declaration before this comment.

**By default, unlisted properties will be ignored.** So if you specify an array and do not include `display`, that means that the `display` property can be included before or after any other property. *This can be changed with the `unspecified` option*.

## Examples

Given:

```js
["transform", "top", "color"]
```

The following patterns are considered warnings:

```css
a {
	color: pink;
	top: 0;
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
	top: 0;
	color: pink;
}
```

```css
a {
	-moz-transform: scale(1);
	-webkit-transform: scale(1);
	transform: scale(1);
}
```

```css
a {
	-webkit-transform: scale(1);
	-moz-transform: scale(1);
	transform: scale(1);
}
```

Given:

```js
["padding", "color", "padding-top"]
```

The following patterns are considered warnings:

```css
a {
	color: pink;
	padding: 1em;
}
```

```css
a {
	padding-top: 1em;
	color: pink;
}
```

The following patterns are *not* considered warnings:

```css
a {
	padding: 1em;
	color: pink;
}
```

```css
a {
	color: pink;
	padding-top: 1em;
}
```

## Further Reading

* [stylelint-order - properties-order](https://github.com/hudochenkov/stylelint-order/blob/master/rules/properties-order/README.md)
