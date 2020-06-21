Pattern: Use of GORM call

Issue: -

## Description

Database operation should be performed by Data Services instead of calling GORM static and instance methods.

Using the GORM static and instance methods may lead to spreading the persistence logic across the whole application instead of concentrating it into services. It makes difficult to find all the code working with the database in case of upgrades to the newer versions of Grails which require all persistence code running inside transactions.

## Examples

``` groovy
class Person {
	String firstName
	String lastName
}

class PersonService {
	
	Person createPerson(String firstName, String lastName) {
		Person person = new Person(firstName: firstName, lastName: lastName)
		return person.save()
	}

}
```

## Further Reading

* [CodeNarc - GrailsDomainGormMethods](https://codenarc.github.io/CodeNarc/codenarc-rules-grails.html#grailsdomaingormmethods-rule)