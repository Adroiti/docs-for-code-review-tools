Pattern: Missing use of fully qualified class name in annotation

Issue: -

## Description

Enforces fully qualified names of classes and interfaces in phpDocs - in annotations. This results in unambiguous phpDocs.

Rule provides the following settings:

* `ignoredAnnotationNames`: case-sensitive list of annotation names that the rule should ignore. Useful for custom annotation names like `@apiParam`

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Namespaces.FullyQualifiedClassNameInAnnotation](https://github.com/slevomat/coding-standard/blob/master/doc/namespaces.md#slevomatcodingstandardnamespacesfullyqualifiedclassnameinannotation-)