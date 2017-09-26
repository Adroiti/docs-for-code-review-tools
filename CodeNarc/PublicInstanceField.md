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

* [CodeNarc - PublicInstanceField](http://codenarc.sourceforge.net/codenarc-rules-design.html#PublicInstanceField)