Pattern: Use of public field

Issue: -

## Description

Using public fields is considered to be a bad design. Use properties instead.

Example of violations:

``` groovy
class Person {
    public String name
}
```

## Further Reading

* [CodeNarc - PublicInstanceField](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#publicinstancefield-rule)