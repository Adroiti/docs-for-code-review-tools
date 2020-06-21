Pattern: Logger for different class

Issue: -

## Description

Checks for instantiating a logger for a class other than the current class. Checks for logger instantiations for **Log4J**, **SLF4J**, **Logback**, **Apache Commons Logging** and **Java Logging API (java.util.logging)**.

This rule contains a parameter `allowDerivedClasses`. When set, a logger may be created about this.getClass().

Limitations:

-   Only checks Loggers instantiated within a class field or property (not variables or expressions within a method)
-   For **Log4J**: Does not catch Logger instantiations if you specify the full package name for the `Logger` class: e.g. `org.apache.log4.Logger.getLogger(..)`
-   For **SLF4J** and **Logback**: Does not catch Log instantiations if you specify the full package name for the `LoggerFactory` class: e.g. `org.slf4j.LoggerFactory.getLogger(..)`
-   For **Commons Logging**: Does not catch Log instantiations if you specify the full package name for the `LogFactory` class: e.g. `org.apache.commons.logging.LogFactory.getLog(..)`
-   For **Java Logging API**: Does not catch Logger instantiations if you specify the full package name for the `Logger` class: e.g. `java.util.logging.Logger.getLogger(..)`

Here are examples of **Log4J** or **Java Logging API** code that cause violations:

``` groovy
class SomeClass {
    private static final LOG = Logger.getLogger(SomeOtherClass)  // violation
    def log1 = Logger.getLogger(SomeOtherClass.class)            // violation
    def log2 = Logger.getLogger(SomeOtherClass.class.name)       // violation
}
```

Here are examples of **Commons Logging** code that cause violations:

``` groovy
class SomeClass {
    private static final LOG = LogFactory.getLog(SomeOtherClass)    // violation
    Log log1 = LogFactory.getLog(SomeOtherClass.class)              // violation
    def log2 = LogFactory.getLog(SomeOtherClass.class.getName())    // violation
}
```

Here are examples of code that does NOT cause violations:

``` groovy
// Log4J or Java Logging API

class SomeClass {
    private static final LOG = Logger.getLogger(SomeClass)                    // ok
    def log2 = Logger.getLogger(SomeClass.class)                              // ok
    private static log3 = Logger.getLogger(SomeClass.getClass().getName())    // ok
    private static log4 = Logger.getLogger(SomeClass.getClass().name)         // ok
    private static log5 = Logger.getLogger(SomeClass.class.getName())         // ok
    private static log6 = Logger.getLogger(SomeClass.class.name)              // ok
}

// Commons Logging

class SomeClass {
    private static final LOG = LogFactory.getLog(SomeClass)                   // ok
    def log2 = LogFactory.getLog(SomeClass.class)                             // ok
    private static log3 = LogFactory.getLog(SomeClass.getClass().getName())   // ok
    private static log4 = LogFactory.getLog(SomeClass.getClass().name)        // ok
    private static log5 = LogFactory.getLog(SomeClass.class.getName())        // ok
    private static log6 = LogFactory.getLog(SomeClass.class.name)             // ok
}
```

## Further Reading

* [CodeNarc - LoggerForDifferentClass](https://codenarc.github.io/CodeNarc/codenarc-rules-logging.html#loggerfordifferentclass-rule)