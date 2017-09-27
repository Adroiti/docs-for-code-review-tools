Pattern: Use of Spock's `@IgnoreRest`

Issue: -

## Description

If Spock's `@IgnoreRest` annotation appears on any method, all non-annotated test methods are not executed. This behaviour is almost always unintended. It's fine to use `@IgnoreRest` locally during development, but when committing code, it should be removed.

The *specificationClassNames* and *specificationSuperclassNames* properties determine which classes are considered Spock *Specification* classes.

| **Property**                 | **Description**                                                                                                                                                                                                                                                                          | **Default Value** |
| --- | --- | --- |
| specificationClassNames      | Specifies one or more (comma-separated) class names that should be treated as Spock Specification classes. The class names may optionally contain wildcards (\*,?), e.g. "\*Spec".                                                                                                       | `null`            |
| specificationSuperclassNames | Specifies one or more (comma-separated) class names that should be treated as Spock Specification superclasses. In other words, a class that extends a matching class name is considered a Spock Specification . The class names may optionally contain wildcards (\*,?), e.g. "\*Spec". | "\*Specification" |

Example of violations:

``` groovy
public class SomeSpec extends spock.lang.Specification {
    @spock.lang.IgnoreRest
    def "first feature"() {
        expect: false
    }

    def "second feature"() {
        given: def a = 2

        when: a *= 2

        then: a == 4
    }
}
```

## Further Reading

* [CodeNarc - SpockIgnoreRestUsed](http://codenarc.sourceforge.net/codenarc-rules-junit.html#SpockIgnoreRestUsed)