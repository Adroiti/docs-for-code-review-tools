Pattern: Unexpected newline in string

Issue: -

## Description

A string cannot directly contain a newline. To include a newline in a string, use an escape representing the line feed character in _ISO-10646_ (`U+000A`), such as `A` or `00000a`. It is possible to break strings over several lines, for aesthetic or other reasons, but in such a case the newline itself has to be escaped with a backslash.

## Examples

The following patterns are considered violations:

```css
a {
  content: "first
    second";     ↑
}                ↑
/**              ↑
 * The newline here */
```

```css
[title="something
is probably wrong"] {}  
```

```css
a {
  font-family: "Times
    New
    Roman";
}  
```

The following patterns are *not* considered violations:

```css
a {
  content: "first\Asecond";     
}  
```

```css
a {
  content: "first\\nsecond";     
}  
```

```css
[title="nothing\
  is wrong"] {}  
```

```css
a {
  font-family: "Times New Roman";
}  
```

## Further Reading

* [stylelint - string-no-newline](https://stylelint.io/user-guide/rules/string-no-newline)