Pattern: Misplaced `default` in `switch` statement

Issue: -

## Description

Java allows `default` anywhere within the `switch` statement, but it is more readable if it comes after the last `case`. 

## Default configuration

```xml
<module name="DefaultComesLast">
    <property name="skipIfLastAndSharedWithCase" value="true"/>
</module>
```

`skipIfLastAndSharedWithCase` - whether to allow `default` along with `case` if they are not last.

## Examples

Example of **incorrect** code:

```java
switch (type) {
    case 1:
        handleTypeOne();
        break;
    default:
        handleUnknownType();
        break;        
    case 2:
        handleTypeTwo();
        break;    
}
```

Example of **correct** code:

```java
switch (type) {
    case 1:
        handleTypeOne();
        break;      
    case 2:
        handleTypeTwo();
        break;
    default:
        handleUnknownType();
        break;          
}
```


## Further Reading

* [checkstyle - DefaultComesLast](https://checkstyle.sourceforge.io/checks/coding/defaultcomeslast.html#DefaultComesLast)
