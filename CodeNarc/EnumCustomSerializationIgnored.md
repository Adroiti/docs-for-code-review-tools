Pattern: Redundant custom Enum serialization

Issue: -

## Description

Checks for enums that define `writeObject()` or `writeReplace()` methods, or declare `serialPersistentFields` or `serialVersionUID` fields, all of which are ignored for enums.

From the javadoc for `ObjectOutputStream`:

*The process by which enum constants are serialized cannot be customized; any class-specific writeObject and writeReplace methods defined by enum types are ignored during serialization. Similarly, any serialPersistentFields or serialVersionUID field declarations are also ignored--all enum types have a fixed serialVersionUID of 0L.*

Example of violations:

``` groovy
enum SomeEnum {
    ONE, TWO, THREE
    private static final long serialVersionUID = 1234567L               // violation
    private static final ObjectStreamField[] serialPersistentFields =   // violation
        { new ObjectStreamField("name", String.class) }
    String name;

    Object writeReplace() throws ObjectStreamException { .. }      // violation
    private void writeObject(ObjectOutputStream stream) { .. }     // violation
}
```

## Further Reading

* [CodeNarc - EnumCustomSerializationIgnored](http://codenarc.sourceforge.net/codenarc-rules-serialization.html#EnumCustomSerializationIgnored)