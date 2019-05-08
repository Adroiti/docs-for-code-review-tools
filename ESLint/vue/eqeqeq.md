Pattern: Missing use of type-safe equality operator

Issue: -

## Description

It is considered good practice to use the type-safe equality operators `===` and `!==` instead of their regular counterparts `==` and `!=`.

The reason for this is that `==` and `!=` do type coercion which follows the rather obscure [Abstract Equality Comparison Algorithm](https://www.ecma-international.org/ecma-262/5.1/#sec-11.9.3).
For instance, the following statements are all considered `true`:

* `[] == false`
* `[] == ![]`
* `3 == "03"`

If one of those occurs in an innocent-looking statement such as `a == b` the actual problem is very difficult to spot.

## Further Reading

* [eslint-plugin-vue - eqeqeq](https://eslint.vuejs.org/rules/eqeqeq.html)
