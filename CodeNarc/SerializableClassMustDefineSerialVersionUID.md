Pattern: `Serializable` class without `serialVersionUID`

Issue: -

## Description

Classes that implement `Serializable` should define a `serialVersionUID`. Deserialization uses this number to ensure that a loaded class corresponds exactly to a serialized object. If you don't define serialVersionUID, the system will make one by hashing most of your class's features. Then if you change anything, the UID will change and Java won't let you reload old data.

An example of a missing serialVersionUID:

``` groovy
class MyClass imlements Serializable {
    // missing serialVersionUID
}
```

## Further Reading

* [CodeNarc - SerializableClassMustDefineSerialVersionUID](http://codenarc.sourceforge.net/codenarc-rules-serialization.html#SerializableClassMustDefineSerialVersionUID)