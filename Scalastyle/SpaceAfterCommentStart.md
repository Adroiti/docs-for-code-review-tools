Pattern: Missing space after comment start

Issue: -

## Description

To bring consistency with how comments should be formatted, leave a space right after the beginning of the comment.

```scala
package foobar

object Foobar {
/**WRONG
*
*/
/** Correct*/
val d = 2 /*Wrong*/ //Wrong
/**
*Correct
*/
val e = 3/** Correct*/ // Correct
}
```

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.SpaceAfterCommentStartChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_SpacesAfterPlusChecker" />

## Further Reading

* [Scalastyle - SpaceAfterCommentStart](https://scalastyle.beautiful-scala.com/rules-1.5.0.html#org_scalastyle_scalariform_SpaceAfterCommentStartChecker)