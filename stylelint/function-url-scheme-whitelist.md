Pattern: Use of non-whitelisted _URL_ scheme

Issue: -

## Description

A [URL scheme](https://url.spec.whatwg.org/#syntax-url-scheme) consists of alphanumeric, `+`, `-`, and `.` characters. It can appear at the start of a URL and is followed by `:`.

This rule treats URL schemes as case insensitive (`https` and `HTTPS` are the same).

This rule ignores URL arguments without an existing URL scheme.

This rule ignores URL arguments with variables or variable interpolation (`$sass`, `@less`, `--custom-property`, `#{$var}`, `@{var}`, `$(var)`).

## Examples

`array|string|regex`: `["array", "of", "schemes" or "regex"]|"scheme"|/regex/`

Given:

```js
["data", "/^http/"]
```

The following patterns are considered violations:

```css
a { background-image: url('http://www.example.com/file.jpg'); }
```

```css
a { background-image: url('file://file.jpg'); }
```

The following patterns are *not* considered violations:

```css
a { background-image: url('example.com/file.jpg'); }
```

```css
a { background-image: url('/example.com/file.jpg'); }
```

```css
a { background-image: url('//example.com/file.jpg'); }
```

```css
a { background-image: url('./path/to/file.jpg'); }
```

```css
a { background-image: url('http://www.example.com/file.jpg'); }
```

```css
a { background-image: url('https://www.example.com/file.jpg'); }
```

```css
a { background-image: url('HTTPS://www.example.com/file.jpg'); }
```

```css
a { background-image: url('data:image/gif;base64,R0lGODlhAQABAIAAAAUEBAAAACwAAAAAAQABAAACAkQBADs='); }
```
