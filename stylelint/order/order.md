Pattern: Wrong content order in declaration block

Issue: -

## Description

Specify the order of content within declaration blocks.

Within an order array, you can include:

- keywords:
	- `custom-properties` — Custom properties (e. g., `--property: 10px;`)
	- `dollar-variables` — Dollar variables (e. g., `$variable`)
	- `at-variables` — At-variables (e. g., `@variable` available in Less syntax)
	- `declarations` — CSS declarations (e. g., `display: block`)
	- `rules` — Nested rules (e. g., `a { span {} }`)
	- `at-rules` — Nested at-rules (e. g., `div { @media () {} }`)
	- `less-mixins` — Mixins in Less syntax (e. g., `.mixin();`)
- extended at-rule objects:

**By default, unlisted elements will be ignored.** So if you specify an array and do not include `declarations`, that means that all declarations can be included before or after any other element. _This can be changed with the `unspecified` option._

## Examples

Given:

```js
["custom-properties", "dollar-variables", "declarations", "rules", "at-rules"]
```

The following patterns are considered warnings:

```css
a {
	top: 0;
	--height: 10px;
	color: pink;
}
```

```css
a {
	@media (min-width: 100px) {}
	display: none;
}
```

The following patterns are _not_ considered warnings:

```css
a {
	--width: 10px;
	$height: 20px;
	display: none;
	span {}
	@media (min-width: 100px) {}
}
```

```css
a {
	--height: 10px;
	color: pink;
	top: 0;
}
```

Given:

```js
[
	{
		type: 'at-rule',
		name: 'include',
	},
	{
		type: 'at-rule',
		name: 'include',
		hasBlock: true
	},
	{
		type: 'at-rule',
		hasBlock: true
	},
	{
		type: 'at-rule',
	}
]
```

The following patterns are considered warnings:

```scss
a {
	@include hello {
		display: block;
	}
	@include hello;
}
```

```scss
a {
	@extend .something;
	@media (min-width: 10px) {
		display: none;
	}
}
```

The following patterns are _not_ considered warnings:

```scss
a {
	@include hello;
	@include hello {
		display: block;
	}
	@media (min-width: 10px) {
		display: none;
	}
	@extend .something;
}
```

```scss
a {
	@include hello {
		display: block;
	}
	@extend .something;
}
```

## Further Reading

* [stylelint-order - order](https://github.com/hudochenkov/stylelint-order/blob/master/rules/order/README.md)
