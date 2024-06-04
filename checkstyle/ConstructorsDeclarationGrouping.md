Pattern: Ungrouped constructors

Issue: -

## Description

Grouping constructors together in a class improves code readability and maintainability. It allows developers to easily understand the different ways an object can be instantiated and the tasks performed by each constructor. 

## Examples

Example of **incorrect** code:

```java
public class Example2 {

  int x;

  Example2() {}

  Example2(String s){}

  void foo() {}

  Example2(int x) {} // violation

  Example2(String s, int x) {} // violation

  private enum ExampleEnum {

    ONE, TWO, THREE;

    ExampleEnum() {}

    ExampleEnum(int x) {}

    final int x = 10;

    ExampleEnum(String str) {} // violation

    void foo() {}
  }

  Example2(float f) {} // violation
}
```

Example of **correct** code:

```java
public class Example1 {

  int x;

  Example1() {}

  Example1(String s) {}

  // comments between constructors are allowed.
  Example1(int x) {}

  Example1(String s, int x) {}

  void foo() {}

  private enum ExampleEnum {

    ONE, TWO, THREE;

    ExampleEnum() {}

    ExampleEnum(int x) {}

    ExampleEnum(String s) {}

    int x = 10;

    void foo() {}
  }
}
```    

## Further Reading

* [checkstyle - ConstructorsDeclarationGrouping](https://checkstyle.sourceforge.io/checks/coding/constructorsdeclarationgrouping.html)
