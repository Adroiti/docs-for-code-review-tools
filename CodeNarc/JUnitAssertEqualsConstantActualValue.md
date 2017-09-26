Pattern: Misused `actual` parameter in `Assert.assertEquals`

Issue: -

## Description

Reports usages of `org.junit.Assert.assertEquals([message,] expected, actual)` where the `actual` parameter is a constant or a literal. Most likely it was intended to be the `expected` value.

Example of violations:

``` groovy
assertEquals(result, 2)
assertEquals("Message", result, 2)
assertEquals(result, 2.3d, 0.5d)
assertEquals("Message", result, 2.3d, 0.5d)
```

## Further Reading

* [CodeNarc - JUnitAssertEqualsConstantActualValue](http://codenarc.sourceforge.net/codenarc-rules-enhanced.html#JUnitAssertEqualsConstantActualValue)