Pattern: Abstract class without abstract method

Issue: -

## Description

The abstract class does not contain any abstract methods. An abstract class suggests an incomplete implementation, which is to be completed by subclasses implementing the abstract methods. If the class is intended to be used as a base class only (not to be instantiated directly) a protected constructor can be provided prevent direct instantiation.

Example:

``` groovy
public abstract class MyBaseClass {
    void method1() {  }
    void method2() {  }
    // consider using abstract methods or removing
    // the abstract modifier and adding protected constructors
}
```

The following examples all pass:

``` groovy
abstract class MyClass extends AbstractParent {
    // OK because parent is named Abstract.*
}
abstract class MyClass extends BaseParent{
    // OK because parent is named Base.*
}
```

## Further Reading

* [CodeNarc - AbstractClassWithoutAbstractMethod](http://codenarc.sourceforge.net/codenarc-rules-design.html#AbstractClassWithoutAbstractMethod)