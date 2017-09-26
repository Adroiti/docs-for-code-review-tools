Pattern: Malformed space around `Map` entry colon

Issue: -

## Description

Check for proper formatting of whitespace around colons for literal `Map` entries. By default, no whitespace is allowed either before or after the Map entry colon, but you can change that through the configuration properties below.

| **Property**              | **Description**                                                                                                                                                                                                                                   | **Default Value**                                |
| --- | --- | --- |
| characterBeforeColonRegex | The regular expression that must match the character before the colon (:) for a literal *Map* entry. For example, `/\S/` matches any non-whitespace character and `/\s/` matches any whitespace character (thus requiring a space or whitespace). | `/\S/` (i.e., no space allowed before the colon) |
| characterAfterColonRegex  | The regular expression that must match the character after the colon (:) for a literal *Map* entry. For example, `/\S/` matches any non-whitespace character and `/\s/` matches any whitespace character (thus requiring a space or whitespace).  | `/\S/` (i.e., no space allowed before the colon) |

Example of violations:

``` groovy
Map m1 = [myKey : 12345]            // violation (both before and after the colon)
println [a :[1:11, 2:22],           // violation on a (before colon)
            b:[(Integer): 33]]      // violation on Integer (after colon)
```

## Further Reading

* [CodeNarc - SpaceAroundMapEntryColon](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#SpaceAroundMapEntryColon)