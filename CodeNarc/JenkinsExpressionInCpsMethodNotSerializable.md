Pattern: Expression in CPS method is not `Serializable`

Issue: -

## Description

Every expression/variable in a CPS transformed method in Jenkins can potentially be serialized and should therefore implement the `Serializable` interface.

Note: The interfaces `List`, `Map` and `Set` are treated as `Serializable` because nearly every implementation is Serializable. It would be bad codestyle to use the implementation as type (see ImplementationAsType Rule).

Known limitations:

    Dynamically typed variables can’t be resolved


## Examples

```groovy
class SomeClass {}
class SerializableClass implements Serializable {}

SomeClass some = new SomeClass() // Violation
SerializableClass ser = new SerializableClass() // OK 
Map map = new HashMap<String, String>() //OK
```

## Further Reading

* [CodeNarc - ExpressionInCpsMethodNotSerializable](https://codenarc.org/codenarc-rules-jenkins.html#expressionincpsmethodnotserializable-rule)