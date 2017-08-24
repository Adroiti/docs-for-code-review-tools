Pattern: Cyclomatic complexity it too high

Issue: -

## Description

Checks cyclomatic complexity against a specified limit. It is a measure of the minimum number of possible paths through the source and therefore the number of required tests, it is not a about quality of code! It is only applied to methods, c-tors, [static initializers and instance initializers](https://docs.oracle.com/javase/tutorial/java/javaOO/initial.html).   
The complexity is equal to the number of decision points `\+ 1` Decision points: `if`, `while` , `do`, `for`, `?:`, `catch` , `switch`, `case` statements, and operators `&&` and `||` in the body of target.   
By pure theory level 1-4 is considered easy to test, 5-7 OK, 8-10 consider re-factoring to ease testing, and 11+ re-factor now as testing will be painful.   
When it comes to code quality measurement by this metric level 10 is very good level as a ultimate target (that is hard to archive). Do not be ashamed to have complexity level 15 or even higher, but keep it below 20 to catch really bad designed code automatically.   
Please use Suppression to avoid violations on cases that could not be split in few methods without damaging readability of code or encapsulation.   


## Examples

To configure the check: 


```xml
<module name="CyclomaticComplexity"/>
```
        

To configure the check with a threshold of 15: 


```xml
<module name="CyclomaticComplexity">
    <property name="max" value="15"/>
</module>
```
        

Explanation on how complexity is calculated (switchBlockAsSingleDecisionPoint is set to false): 


```java
class CC {
   // Cyclomatic Complexity = 12
   public void doSmth()  {  // 1
       if (a == b)  {       // 2
   if (a1 == b1             // 3
   && c1 == d1) {   // 4
  fiddle();
   }
   else if (a2 == b2        // 5
         || c1 < d1) {   // 6
   fiddle();
   }
   else {
   fiddle();
   }
       }
        else if (c == d) {  // 7
   while (c == d) {         // 8
   fiddle();
   }
        }
else if (e == f) {
   for (n = 0; n < h     // 9
       || n < 6; n++) {  // 10
   fiddle();
   }
        }
        else {
   switch (z) {
 case 1:                    // 11
       fiddle();
       break;
 case 2:                    // 12
       fiddle();
       break;
 default:
       fiddle();
       break;
   }
        }
    }
}        
```

Explanation on how complexity is calculated (switchBlockAsSingleDecisionPoint is set to true): 


```java
class SwitchExample {
   // Cyclomatic Complexity = 2
   public void doSmth()  {            // 1
       int z = 1;
       switch (z) {      // 2
  case 1:
  foo1();
  break;
  case 2:
  foo2();
  break;
  default:
  fooDefault();
  break;
       }
   }
}
```

## Further Reading

* [checkstyle - CyclomaticComplexity](http://checkstyle.sourceforge.net/config_metrics.html#CyclomaticComplexity)
