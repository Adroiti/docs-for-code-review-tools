Pattern: Use of scheme-relative _URL_

Issue: -

## Description

Disallow scheme-relative urls. A [scheme-relative URL](https://url.spec.whatwg.org/#syntax-url-scheme-relative) is a URL that begins with `//` followed by a host.

This rule ignores URL arguments that are variables (`$sass`, `@less`, `--custom-property`).

## Examples

The following patterns are considered violations:

```css
a { background-image: url('//www.google.com/file.jpg'); }
/**                        ↑ 
 *  This scheme-relative url */
```

The following patterns are *not* considered violations:

```css
a { 
  background: url("../file.jpg"); 
}
```

```css
a { 
  background: url("http://www.google.com/file.jpg"); 
}
```

```css
a { 
  background: url("/path/to/file.jpg"); 
}
```

## Further Reading

* [stylelint - function-url-no-scheme-relative](https://stylelint.io/user-guide/rules/function-url-no-scheme-relative)