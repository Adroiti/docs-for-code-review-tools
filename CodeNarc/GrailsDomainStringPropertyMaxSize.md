Pattern: Grails - missing maximum size for domain string

Issue: -

## Description

String properties in Grails domain classes have to define maximum size otherwise the property is mapped to `VARCHAR(255)` causing runtime exceptions to occur. To fix this issue either declare `size` or `maxSize` constraint for the property inside `constraints` DSL closure of your Grails domain class or declare the `type` of the property inside `mapping` DSL closure. If you use the second option inside **mapping** DSL closure then please pay attention that the value of `type` is not
checked so using for example `VARCHAR(50)` would still cause runtime exceptions.

Example of violations:

``` groovy
// both firstName and lastName will probably have database limit of 255 characters
// which is not validated by Grails validation causing runtime JDBC exception
class Person {

    String firstName
    String lastName

    static constraints = {
        firstName nullable:true
        lastName nullable:true
    }
}
```

Example of valid configuration:

``` groovy
class Person {

    String firstName
    String lastName

    static constraints = {
        firstName nullable:true, maxSize: 255
        lastName nullable:true
    }

    static mapping = {
        lastName type: 'text'
    }
}
```

## Further Reading

* [CodeNarc - GrailsDomainStringPropertyMaxSize](http://codenarc.sourceforge.net/codenarc-rules-grails.html#GrailsDomainStringPropertyMaxSize)