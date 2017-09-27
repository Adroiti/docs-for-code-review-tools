Pattern: Invalid factory method name

Issue: -

## Description

A factory method is a method that creates objects, and they are typically named either `buildFoo()`, `makeFoo()`, or `createFoo()`. This rule enforces that only one naming convention is used. It defaults to allowing `makeFoo()`, but that can be changed using the property `regex`. The regex is a negative expression; it specifically bans methods named build\* or create\*. However, methods named build or build\* receive some special treatment because of the popular Builder Pattern. If the 'build' method is in a class named \*Builder then it does not cause a violation.

Builder methods are slightly different than factory methods.

| **Property** | **Description**                                                                                                        | **Default Value**      |
| --- | --- | --- |
| regex        | Specifies the default regular expression used to validate the method name. It is required and cannot be null or empty. | /(build.\*|create.\*)/ |

Example of violations:

``` groovy
class SomeClass {

    // violation. Factory methods should be named make()
    def create() {
    }

    // violation. Factory methods should be named make()
    def createSomething() {
    }

    // violation. Builder method not in class named *Builder
    def build() {
    }

    // violation. Builder method not in class named *Builder
    def buildSomething() {
    }

    // this is OK because it is called make
    def make() {
    }

    // this is also OK
    def makeSomething() {
    }

    // OK, overriding a parent
    @Override
    build() { }

}

class WidgetBuilder {

    // OK, the class name ends in Builder
    def build() {
    }
}
```

## Further Reading

* [CodeNarc - FactoryMethodName](http://codenarc.sourceforge.net/codenarc-rules-naming.html#FactoryMethodName)