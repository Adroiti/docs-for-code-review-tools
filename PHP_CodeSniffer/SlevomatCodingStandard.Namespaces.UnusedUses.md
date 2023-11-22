Pattern: Unused import

Issue: -

## Description

Looks for unused imports from other namespaces.

Rule provides the following settings:

* `searchAnnotations` (defaults to `false`): enables searching for class names in annotations.
* `ignoredAnnotationNames`: case-sensitive list of annotation names that the rule should ignore (only the name is ignored, annotation content is still searched). Useful for name collisions like `@testCase` annotation and `TestCase` class.
* `ignoredAnnotations`: case-sensitive list of annotation names that the rule ignore completely (both name and content are ignored). Useful for name collisions like `@group Cache` annotation and `Cache` class.

## Further Reading

* [PHP_CodeSniffer - SlevomatCodingStandard.Namespaces.UnusedUses](https://github.com/slevomat/coding-standard/blob/master/doc/namespaces.md#slevomatcodingstandardnamespacesunuseduses-)