Pattern: Class is not Serializable

Issue: -

## Description

Classes in Jenkins libraries should generally implement the `Serializable` interface because every expression/variable used in a CPS transformed method can potentially be serialized. 

Generally all user defined classes (not from external libraries) in pipeline libraries or Jenkins files are already implicitly `Serializable` in Jenkins but it makes static analysis easier later on if all classes are marked `Serializable` explicitly.

## Further Reading

* [CodeNarc - ClassNotSerializable](https://codenarc.org/codenarc-rules-jenkins.html#classnotserializable-rule)