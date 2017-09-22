Pattern: Lowercase pattern match

Issue: -

## Description

A lower case pattern match clause with no other tokens is the same as `_`. This is not true for patterns which start with an upper case letter. This can cause confusion, and may not be what was intended:

    val foo = "foo"
    val Bar = "bar"
    "bar" match { case Bar => "we got bar" }   // result = "we got bar"
    "bar" match { case foo => "we got foo" }   // result = "we got foo"
    "bar" match { case `foo` => "we got foo" } // result = MatchError

This rule raises a warning with the second match. To fix it, use an identifier which starts with an upper case letter (best), use `case _` or, if you wish to refer to the value, add a type `: Any`

    val lc = "lc"
    "something" match { case lc: Any => "lc" } // result = "lc"
    "something" match { case _ => "lc" } // result = "lc"

## Example configuration
<pre>&lt;check enabled=&quot;true&quot; class=&quot;org.scalastyle.scalariform.LowercasePatternMatchChecker&quot; level=&quot;warning&quot;/&gt;</pre>
<a name="org_scalastyle_scalariform_MagicNumberChecker" />

## Further Reading

* [Scalastyle - LowercasePatternMatch](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_LowercasePatternMatchChecker)