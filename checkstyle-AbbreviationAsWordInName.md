Pattern: Too many consecutive capital letters in identifier

Issue: -

## Description

This check validates abbreviation (consecutive capital letters) length in identifier name. It also allows to enforce camel case naming. Please read more at [Google Style Guide](http://checkstyle.sourceforge.net/reports/google-java-style-20170228.html#s5.3-camel-case) to get to know how to avoid long abbreviations in names. 

_allowedAbbreviationLength_ specifies how many consecutive capital letters are allowed in the identifier. A value of _3_ indicates that up to 4 consecutive capital letters are allowed, one after the other, before a violation is printed. The identifier 'MyTEST' would be allowed, but 'MyTESTS' would not be. A value of _0_ indicates that only 1 consecutive capital letter is allowed. This is what should be used to enforce strict camel casing. The identifier 'MyTest' would be allowed, but 'MyTEst' would not be. 

## Examples

Default configuration 


```xml
<module name="AbbreviationAsWordInName"/>
```


To configure to check variables and classes identifiers, do not ignore variables with static modifier and allow no abbreviations (enforce camel case phrase) and allow no abbreviations to use (camel case phrase) and allow XML and URL abbreviations. 


```xml
<module name="AbbreviationAsWordInName">
    <property name="tokens" value="VARIABLE_DEF,CLASS_DEF"/>
    <property name="ignoreStatic" value="false"/>
    <property name="allowedAbbreviationLength" value="1"/>
    <property name="allowedAbbreviations" value="XML,URL"/>
</module>
```

## Further Reading

* [checkstyle - AbbreviationAsWordInName](http://checkstyle.sourceforge.net/config_naming.html#AbbreviationAsWordInName)
