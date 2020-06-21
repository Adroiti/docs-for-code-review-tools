Pattern: Overload of `equals()`

Issue: -

## Description

The class has an `equals` method, but the parameter of the method is not of type `Object`. It is not overriding `equals` but instead overloading it.

Example of violations:

``` groovy
class Object1 {
    //parameter should be Object not String
    boolean equals(String other) { true }
}

class Object2 {
    // Overloading equals() with 2 parameters is just mean
    boolean equals(Object other, String other2) { true }
}

class Object3 {
    // a no-arg equals()? What is this supposed to do?
    boolean equals() { true }
}


// all of these are OK and do not cause violations
class Object4 {
    boolean equals(Object other) { true }
}

@SuppressWarnings('EqualsOverloaded')
class Object5 {
    boolean equals(String other) { true }
}

class Object6 {
    boolean equals(java.lang.Object other) { true }
}

class Object7 {
    boolean equals(other) { true }
}
```

## Further Reading

* [CodeNarc - EqualsOverloaded](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#equalsoverloaded-rule)