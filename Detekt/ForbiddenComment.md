Pattern: Unresolved warning comment

Issue: -

## Description

Developers often add comments to code which is not complete or needs review. Most likely you want to fix or review the code, and then remove the comment, before you consider the code to be production ready.

Example of **incorrect** code:

```kotlin
// TODO:,FIXME:,STOPSHIP:
fun foo() { }
```

## Further Reading

* [Detekt - ForbiddenComment](https://detekt.dev/docs/rules/style/#forbiddencomment)