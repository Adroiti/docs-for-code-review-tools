Pattern: Invalid `catch` parameter name

Issue: -

## Description

Checks that `catch` parameter names conform to a format specified by the format property. Default pattern has the following characteristic: 

  - allows names beginning with two lowercase letters followed by at least one uppercase or lowercase letter
  - allows `e` abbreviation (suitable for exceptions end errors)
  - allows `ex` abbreviation (suitable for exceptions)
  - allows `t` abbreviation (suitable for throwables)
  - prohibits numbered abbreviations like `e1` or `t2`
  - prohibits one letter prefixes like `pException`
  - prohibits two letter abbreviations like `ie` or `ee`
  - prohibits any other characters than letters

## Examples

To configure the check: 


```xml
<module name="CatchParameterName"/>
```
        

An example of how to configure the check for names that begin with a lower case letter, followed by letters and digits is: 


```xml
<module name="CatchParameterName">
    <property name="format" value="^[a-z][a-zA-Z0-9]+$"/>
</module>
```

## Further Reading

* [checkstyle - CatchParameterName](http://checkstyle.sourceforge.net/config_naming.html#CatchParameterName)
