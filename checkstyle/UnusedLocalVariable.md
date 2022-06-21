Pattern: Unused local variable

Issue: -

## Description

Checks that a local variable is declared and/or assigned, but not used. Doesn't support pattern variables yet. Doesn't check array components as array components are classified as different kind of variables by JLS. 


```java
class Test {

    int a;

    {
        int k = 12; // violation, assigned and updated but never used
        k++;
    }

    Test(int a) {   // ok as 'a' is a constructor parameter not a local variable
        this.a = 12;
    }

    void method(int b) {
        int a = 10;             // violation
        int[] arr = {1, 2, 3};  // violation
        int[] anotherArr = {1}; // ok
        anotherArr[0] = 4;
    }
}
```
        

## Examples

To configure the check: 


```xml
<module name="UnusedLocalVariable"/>
```

## Further Reading

* [checkstyle - UnusedLocalVariable](https://checkstyle.sourceforge.io/config_coding.html#UnusedLocalVariable)
