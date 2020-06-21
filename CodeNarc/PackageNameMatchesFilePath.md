Pattern: Mismatch for package name and file path

Issue: -

## Description

A package source file's path should match the package declaration.

| **Property** | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | **Default Value** |
| --- | --- | --- |
| groupId      | Specifies the common *group id* part of a package name, that will appear within all checked package names. It must also map to the file path for the corresponding source file. For instance, a *groupId* of *"org.sample"* means that for all classes that specify a package, that package name must include *"org.sample"*, and the source file must exist under an "org/sample" directory. Then, a `SomeClass` class in a `org.sample.util` package must be defined in a "SomeClass.groovy" file within a *"org/sample/util"* directory. That directory can be the child of any arbitrary *root path*, e.g. "src/main/groovy". To find the sub-path relevant for the package the rule searches for the first appearance of *groupId* in the file path. It's *required* to configure this. If `groupId` is null or empty, this rule does nothing. | `null`            |

## Further Reading

* [CodeNarc - PackageNameMatchesFilePath](https://codenarc.github.io/CodeNarc/codenarc-rules-naming.html#packagenamematchesfilepath-rule)