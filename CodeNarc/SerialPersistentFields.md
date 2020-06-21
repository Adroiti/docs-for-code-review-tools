Pattern: `serialPersistentFields` is not `private`, `static`, and `final`

Issue: -

## Description

To use a **Serializable** object's `serialPersistentFields` correctly, it must be declared `private`, `static`, and `final`.

The Java Object Serialization Specification allows developers to manually define `Serializable` fields for a class by specifying them in the `serialPersistentFields` array. This feature will only work if `serialPersistentFields` is declared as `private`, `static`, and `final`. Also, specific to Groovy, the field must be of type `ObjectStreamField[]`, and cannot be `Object`.

Example of violations:

``` groovy
class SomeClass implements Serializable {
    public ObjectStreamField[] serialPersistentFields = [ new ObjectStreamField("someField", List.class) ] as ObjectStreamField[]
}

// the JVM sees the field type as Object, which won't work
class SomeOtherClass implements Serializable {
    private static final serialPersistentFields = [ new ObjectStreamField("someField", List.class) ] as ObjectStreamField[]
}
```

## Further Reading

* [CodeNarc - SerialPersistentFields](https://codenarc.github.io/CodeNarc/codenarc-rules-serialization.html#serialpersistentfields-rule)