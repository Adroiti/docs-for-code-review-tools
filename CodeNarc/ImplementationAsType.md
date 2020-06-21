Pattern: Implementation as type

Issue: -

## Description

Checks for use of the following concrete classes when specifying the type of a method parameter, closure parameter, constructor parameter, method return type or field type. The corresponding interfaces should be used to specify the type instead.

-   java.util.ArrayList
-   java.util.GregorianCalendar
-   java.util.HashMap
-   java.util.HashSet
-   java.util.Hashtable
-   java.util.LinkedHashMap
-   java.util.LinkedHashSet
-   java.util.LinkedList
-   java.util.TreeMap
-   java.util.TreeSet
-   java.util.Vector
-   java.util.concurrent.ArrayBlockingQueue
-   java.util.concurrent.ConcurrentHashMap
-   java.util.concurrent.ConcurrentLinkedQueue
-   java.util.concurrent.CopyOnWriteArrayList
-   java.util.concurrent.CopyOnWriteArraySet
-   java.util.concurrent.DelayQueue
-   java.util.concurrent.LinkedBlockingQueue
-   java.util.concurrent.PriorityBlockingQueue
-   java.util.concurrent.PriorityQueue
-   java.util.concurrent.SynchronousQueue

Here are examples of code that produces violations:

``` groovy
// Method parameter
void someMethod(ArrayList list) {                   // violation
    ...
}

// Constructor parameter
class SomeClass {
    SomeClass(java.util.HashSet set) {              // violation
        ...
    }
}

// Closure parameter
def closure = { PriorityQueue queue -> ... }      // violation

// Method return type
GregorianCalendar calculateDate(int num) {        // violation
    ...
}

// Field type
class SomeClass {
    Hashtable map                                 // violation
}
```

## Further Reading

* [CodeNarc - ImplementationAsType](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#implementationastype-rule)