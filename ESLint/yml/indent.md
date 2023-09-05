Pattern: Inconsistent indentation

Issue: -

## Description

This rule reports enforces a consistent indentation style. The default style is 2 spaces.

```js
# eslint yml/indent: 'error'

# ✓ GOOD
- a:
    b
  c:
    - d
    - e: f
      g: h

# ✗ BAD
- a:
   b
  c:
   - d
   -  e: f
      g: h
```

## Further Reading

* [yml/indent](https://ota-meshi.github.io/eslint-plugin-yml/rules/indent.html)