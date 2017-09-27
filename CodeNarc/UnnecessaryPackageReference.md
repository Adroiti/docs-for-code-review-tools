Pattern: Unnecessary package reference

Issue: -

## Description

Checks for explicit package reference for classes that Groovy imports by default, such as `java.lang.String`, `java.util.Map` and `groovy.lang.Closure`, as well as classes that were explicitly imported.

You do not need to specify the package for any classes from *java.lang*, *java.util*, *java.io*, *java.net*, *groovy.lang* and *groovy.util*, as well as the classes *java.math.BigDecimal* and *java.math.BigInteger*.

Examples of violations include:

``` groovy
// Field types
class MyClass {
    java.math.BigDecimal amount = 42.10                     // violation
}

// Within expressions
if (value.class == java.math.BigInteger) { }                // violation
println "isClosure=${v instanceof groovy.lang.Closure}"     // violation
def p = java.lang.Runtime.availableProcessors()             // violation

// Constructor calls
def url = new java.net.URL('http://abc@example.com')        // violation

// Variable types
void doSomething() {
    java.math.BigInteger maxValue = 0                       // violation
    java.net.URI uri                                        // violation
}

// Method return types
java.io.Reader getReader() { }                              // violation
groovy.util.AntBuilder getAntBuilder() { }                  // violation

// Method parameter types
void writeCount(java.io.Writer writer, int count) { }       // violation
void init(String name, groovy.lang.Binding binding) { }     // violation

// Closure parameter types
def writeCount = { java.io.Writer writer, int count -> }    // violation

// Extends and implements
class MyHashMap extends java.util.HashMap { }               // violation
class MyList implements java.util.List { }                  // violation

// Explicitly imported classes
import javax.servlet.http.Cookie
import javax.sql.DataSource

class MyClass {
    void doStuff(javax.servlet.http.Cookie cookie) {        // violation
        def dataSource = [:] as javax.sql.DataSource        // violation
    }
}
```

Known limitations:

-   Does not catch class declarations that explicitly extend `java.lang.Object`. For instance, `class MyClass extends java.lang.Object  `. Just don't do that, okay?
-   Does not catch class declarations that explicitly extend `groovy.lang.Script`. For instance, `class MyScript extends groovy.lang.Script `. Don't do that, either!
-   Does not catch unnecessary package references if they are the types of anonymous inner class definitions, for older versions of Groovy ( *1.7.10?). For instance, &lt;&lt;&lt;def runnable = new java.lang.Runnable() <span id="a...">...</span>*&gt;&gt;.

## Further Reading

* [CodeNarc - UnnecessaryPackageReference](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryPackageReference)