Pattern: Unnecessary object reference

Issue: -

## Description

Violations are triggered when an excessive set of consecutive statements all reference the same variable. This can be made more readable by using a `with` or `identity` block. By default, 5 references are allowed. You can override this property using the **maxReferencesAllowed** property on the rule.

These two bits of code produce violations:

``` groovy
def p1 = new Person()
p1.firstName = 'Hamlet'
p1.lastName = "D'Arcy"
p1.employer = 'Canoo'
p1.street = 'Kirschgaraten 5'
p1.city = 'Basel'
p1.zipCode = '4051'

def p2 = new Person()
p2.setFirstName('Hamlet')
p2.setLastName("D'Arcy")
p2.setEmployer('Canoo')
p2.setStreet('Kirschgaraten 5')
p2.setCity('Basel')
p2.setZipCode('4051')
```

However, these two bits of code do not because they use either a `with` or `identity` block.

``` groovy
def p1 = new Person().with {
    firstName = 'Hamlet'
    lastName = "D'Arcy"
    employer = 'Canoo'
    street = 'Kirschgaraten 5'
    city = 'Basel'
    zipCode = '4051'
}

def p2 = new Person().identity {
    firstName = 'Hamlet'
    lastName = "D'Arcy"
    employer = 'Canoo'
    street = 'Kirschgaraten 5'
    city = 'Basel'
    zipCode = '4051'
}
```

## Further Reading

* [CodeNarc - UnnecessaryObjectReferences](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessaryobjectreferences-rule)