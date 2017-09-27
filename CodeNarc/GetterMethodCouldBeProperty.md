Pattern: Getter method not property

Issue: -

## Description

If a class defines a `public` method that follows the Java getter notation and that returns a constant, then it is cleaner to provide a Groovy property for the value rather than a Groovy method.

| **Property**                        | **Description**                                                | **Default Value** |
| --- | --- | --- |
| ignoreMethodsWithOverrideAnnotation | If `true`, then do not check methods annotated with `@Override`. | `false`           |

Example of violations:

``` groovy
interface Parent {
    String getSomething()
    String getSomethingElse()
}

class Child extends Parent {
    static VALUE = 'value'

    @Override
    String getSomething() {
        'something'         // this could be simplified
    }

    @Override
    String getSomethingElse() {
        VALUE       // this could be simplified
    }

    int getOtherValue() {
        123
    }

    static String getName() {
        'SomeName'
    }
}

class Child2 extends Parent {
    static VALUE = 'value'
    final String something = 'something'    // this is cleaner
    final String somethingElse = VALUE      // this is cleaner
    final int otherValue = 123              // this is cleaner
    static final String name = 'SomeName'     // this is cleaner
}
```

## Further Reading

* [CodeNarc - GetterMethodCouldBeProperty](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#GetterMethodCouldBeProperty)