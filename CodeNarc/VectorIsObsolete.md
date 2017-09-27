Pattern: Use of `Vector`

Issue: -

## Description

Checks for references to the (*effectively*) obsolete `java.util.Vector` class. Use the **Java Collections Framework** classes instead, including `ArrayList` or `Collections.synchronizedList()`.

Note: As of the Java 2 platform v1.2, this class was retrofitted to implement the List interface, making it a member of the Java Collections Framework. Unlike the new collection implementations, Vector is synchronized. If a thread-safe implementation is not needed, it is recommended to use `ArrayList` in place of `Vector`.

Example of violations:

``` groovy
def someList = new Vector()           // violation
```

## Further Reading

* [Stack Overflow - Why is Java Vector class considered obsolete or deprecated?](https://stackoverflow.com/questions/1386275/why-is-java-vector-class-considered-obsolete-or-deprecated)
* [Java API Specification - Vector](https://docs.oracle.com/javase/8/docs/api/java/util/Vector.html)
* [CodeNarc - VectorIsObsolete](http://codenarc.sourceforge.net/codenarc-rules-convention.html#VectorIsObsolete)