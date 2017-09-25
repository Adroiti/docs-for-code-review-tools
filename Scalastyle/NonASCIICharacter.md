Pattern: Non-English character

Issue: -

## Description

Scala allows unicode characters as operators and some editors misbehave when they see non-ascii character. This rule can be helpful in such situations.

```scala
"value".match {
case "value" => println("matched")
...
}

is preferred to

"value".match {
case "value" ⇒ println("matched")
...
}
```

To fix it, replace the (unicode operator)`⇒` with `=>`.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.NonASCIICharacterChecker" level="warning"/>
```
<a name="org_scalastyle_scalariform_NotImplementedErrorUsage" />

## Further Reading

* [Scalastyle - NonASCIICharacter](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_NonASCIICharacterChecker)