Pattern: Lambda body is too long

Issue: -

## Description

Similar to anonymous inner classes, if lambda body becomes very long it is hard to understand and to see the flow of the method where the lambda is defined. Therefore long lambda body should usually be extracted to method. 

## Examples

```java
class Test {
  Runnable r = () -> { // violation, 11 lines
      System.out.println(2); // line 2 of lambda
      System.out.println(3);
      System.out.println(4);
      System.out.println(5);
      System.out.println(6);
      System.out.println(7);
      System.out.println(8);
      System.out.println(9);
      System.out.println(10);
  }; // line 11

  Runnable r2 = () -> // violation, 11 lines
      "someString".concat("1") // line 1 of lambda
                  .concat("2")
                  .concat("3")
                  .concat("4")
                  .concat("5")
                  .concat("6")
                  .concat("7")
                  .concat("8")
                  .concat("9")
                  .concat("10")
                  .concat("11"); // line 11

  Runnable r3 = () -> { // ok, 10 lines
      System.out.println(2); // line 2 of lambda
      System.out.println(3);
      System.out.println(4);
      System.out.println(5);
      System.out.println(6);
      System.out.println(7);
      System.out.println(8);
      System.out.println(9);
  }; // line 10
}
    
```


## Further Reading

* [checkstyle - LambdaBodyLength](https://checkstyle.org/config_sizes.html#LambdaBodyLength)