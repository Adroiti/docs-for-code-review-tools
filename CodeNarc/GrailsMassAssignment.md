Pattern: Grails - mass assignment

Issue: -

## Description

Untrusted input should not be allowed to set arbitrary object fields without restriction.

Example of violations:

``` groovy
   // Person would be a grails domain object
   def person = new Person(params)
   person.save()

   // or using .properties
   def person = Person.get(1)
   person.properties = params
   person.save()
```

## Further Reading

* [CodeNarc - GrailsMassAssignment](https://codenarc.github.io/CodeNarc/codenarc-rules-grails.html#grailsmassassignment-rule)