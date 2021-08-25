Pattern: Use of whitespace before `:` in `switch`

Issue: -

## Description

Checks that there is no whitespace before the colon in a switch block. 

## Examples

```java
class Test {
  {
    switch(1) {
        case 1 : // violation, whitespace before ':' is not allowed here
            break;
        case 2: // ok
            break;
        default : // violation, whitespace before ':' is not allowed here
            break;
    }

    switch(2) {
        case 2: // ok
            break;
        case 3, 4
                 : break; // violation, whitespace before ':' is not allowed here
        case 4,
              5: break; // ok
        default
              : // violation, whitespace before ':' is not allowed here
            break;
    }

    switch(day) {
        case MONDAY, FRIDAY, SUNDAY: System.out.println("  6"); break;
        case TUESDAY               : System.out.println("  7"); break; // violation
    }
}
```
        

To configure the check to ignore `&` and `|`: 


```xml
<module name="NoWhitespaceBeforeCaseDefaultColon"/>
```

## Further Reading

* [checkstyle - NoWhitespaceBeforeCaseDefaultColon](https://checkstyle.sourceforge.io/config_whitespace.html#NoWhitespaceBeforeCaseDefaultColon)
