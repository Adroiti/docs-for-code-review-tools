Pattern: Builder method with side effects

Issue: -

## Description

A builder method is defined as one that creates objects. As such, they should never be of `void` return type. If a method is named `build`, `create`, or `make`, then it should always return a value.

This rule has one property: `methodNameRegex`. The default value is `(make.*|create.*|build.*)`. Update this property if you have some other naming convention for your builder methods.

Example of violations:

``` groovy
class MyClass {

        void make() { /* ... */ }
        void makeSomething() { /* ... */ }

        void create() { /* ... */ }
        void createSomething() { /* ... */ }

        void build() { /* ... */ }
        void buildSomething() { /* ... */ }
}
```

## Further Reading

* [CodeNarc - BuilderMethodWithSideEffects](http://codenarc.sourceforge.net/codenarc-rules-design.html#BuilderMethodWithSideEffects)