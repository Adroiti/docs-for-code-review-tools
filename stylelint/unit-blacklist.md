Pattern: Use of blacklisted unit

Issue: -

## Description

Specify a blacklist of disallowed units.

## Examples

`array|string`: `["array", "of", "units"]|"unit"`

Given:

```js
["px", "em", "deg"]
```

The following patterns are considered violations:

```css
a { width: 100px; }
```

```css
a { font-size: 10em; }
```

```css
a { transform: rotate(30deg); }
```

The following patterns are *not* considered violations:

```css
a { font-size: 1.2rem; }
```

```css
a { line-height: 1.2; }
```

```css
a { height: 100vmin; }
```

```css
a { animation: animation-name 5s ease; }
```

# Configuration

### `ignoreProperties: { unit: ["property", "/regex/"] }`

Ignore units in the values of declarations with the specified properties.

For example, with `["px", "vmin"]`.

Given:

```js
{
  "px": [ "font-size", "/^border/" ],
  "vmin": [ "width" ]  
}
```

The following patterns are *not* considered violations:

```css
a { font-size: 13px; }
```

```css
a { border-bottom-width: 6px; }
```

```css
a { width: 100vmin; }
```

The following patterns are considered violations:

```css
a { line-height: 12px; }
```

```css
a { -moz-border-radius-topright: 40px; }
```

```css
a { height: 100vmin; }
```
