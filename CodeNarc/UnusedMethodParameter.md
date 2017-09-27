Pattern: Unused method parameter

Issue: -

## Description

This rule finds instances of method parameters not being used. It does not analyze private methods or methods marked `@Override`.

-   This rule ignores `main()` methods. In Groovy, the `main()>> method can either specify a <<<void` return type or else omit a return type (be dynamically typed). The `main()>> method must have exactly one parameter. That parameter can either be typed as <<<String[]` or else the type can be omitted (be dynamically typed). And the `main()>> method must be <<<static`.
-   You can specify an ignore list of parameter names using the `ignoreRegex` property. By default, a parameter named `ignore` or `ignored` does not trigger a violation (the regex value is `ignore|ignored`). You can add your own ignore list using this property.
-   You can specify a class name pattern to ignore using the `ignoreClassRegex` property. By default classes named `\*.Category` are ignored because they are category classes and have unused parameters in static methods.


Example of violations:

``` groovy
    class MyClass {
        def method(def param) {
            // param is unused
        }
    }
```

Example of code that does not cause violations:

``` groovy
    class MyClass {
        @Override
        def otherMethod(def param) {
            // this is OK because it overrides a super class
        }
    }

    class MyCategory {
        // Category classes are ignored by default
        void myMethod1(String string, int value) { }
        void myMethod1(String string, int value, name) { }
    }

    class MainClass1 {
        // main() methods are ignored
        public static void main(String[] args) { }
    }
    class MainClass2 {
        // This is also a valid Groovy main() method
        static main(args) { }
    }
```

## Further Reading

* [CodeNarc - UnusedMethodParameter](http://codenarc.sourceforge.net/codenarc-rules-unused.html#UnusedMethodParameter)