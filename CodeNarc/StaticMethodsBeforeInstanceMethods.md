Pattern: Use of instance method before static method

Issue: -

## Description

Enforces that all static methods within each visibility level (`public`, `protected`, `private`) are above all instance methods within that same visibility level. In other words, public static methods must be above public instance methods, protected static methods must be above protected instance methods and private static methods must be above private instance methods.

Example of violations:

``` groovy
    class MyClass {
        // Public
        public static int staticMethod1() { }
        public String method1() { }
        int method2() { }
        static final String staticMethod2(int id) { }       // violation

        // Protected
        protected String method3() { }
        protected static staticMethod3() { }                // violation

        // Private
        private int method4() { }
        private int method5() { }
        private static staticMethod4() { }                  // violation
        private String method5() { }
    }
}
```

## Further Reading

* [CodeNarc - StaticMethodsBeforeInstanceMethods](http://codenarc.sourceforge.net/codenarc-rules-convention.html#StaticMethodsBeforeInstanceMethods)