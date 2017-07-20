Pattern: Missing override for `equals()` or `hashCode()`

Issue: -

## Description

The contract of `equals()` and `hashCode()` requires that equal objects have the same hashCode. Therefore, whenever you override `equals()` you must override `hashCode()` to ensure that your class can be used in hash-based collections. 

## Default configuration

```xml
<module name="EqualsHashCode"/>
```

## Examples

Example of **incorrect** code:

```java
public class User {
    private String name;
    private int age;

    @Override
    public int hashCode() {
        int result = 17;
        result = 31 * result + name.hashCode();
        result = 31 * result + age;
        return result;
    }
}
```

Example of **correct** code:

```java
public class User {
    private String name;
    private int age;

    @Override
    public int hashCode() {
        int result = 17;
        result = 31 * result + name.hashCode();
        result = 31 * result + age;
        return result;
    }
    
    @Override
    public boolean equals(Object o) {
        if (o == this) return true;
        if (!(o instanceof User)) {
            return false;
        }

        User user = (User) o;
        return user.name.equals(name) && user.age == age;
    }
}
```

## Further Reading

* [Stack Overflow - What issues should be considered when overriding equals and hashCode in Java?
](https://stackoverflow.com/questions/27581/what-issues-should-be-considered-when-overriding-equals-and-hashcode-in-java)
* [checkstyle - EqualsHashCode](http://checkstyle.sourceforge.net/config_coding.html#EqualsHashCode)
