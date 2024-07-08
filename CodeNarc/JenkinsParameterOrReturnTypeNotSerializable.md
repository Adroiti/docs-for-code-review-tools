Pattern: Parameter or return type is not `Serializable`

Issue: -

## Description

Every parameter and return type has to implement the `Serializable` interface in Jenkins CPS tranformed Code.

## Examples

```groovy
class SomeClass {}
class SerializableClass implements Serializable {}

void method(int i, SomeClass s) {}                                // Violation
SomeClass returnMethod() { return null }                          // Violation
SerializableClass safeMethod(SerializableClass s) { return null } // OK
```

## Further Reading

* [CodeNarc - ParameterOrReturnTypeNotSerializable](https://codenarc.org/codenarc-rules-jenkins.html#parameterorreturntypenotserializable-rule)