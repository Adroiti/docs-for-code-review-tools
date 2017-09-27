Pattern: Grails - duplicate mapping

Issue: -

## Description

Checks for duplicate name in a Grails domain class mapping. Duplicate names/entries are legal, but can be confusing and error-prone.

NOTE: This rule does not check that the values of the entries are duplicated, only that there are two entries with the same name.

Example of violations:

``` groovy
class Person {
    String firstName
    String lastName

    static mapping = {
        table 'people'
        firstName column: 'First_Name'
        lastName column: 'Last_Name'
        firstName column: 'First_Name'      // violation
        table 'people2'                     // violation
    }
}
```

## Further Reading

* [CodeNarc - GrailsDuplicateMapping](http://codenarc.sourceforge.net/codenarc-rules-grails.html#GrailsDuplicateMapping)