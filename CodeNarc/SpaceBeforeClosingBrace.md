Pattern: Malformed space before `}`

Issue: -

## Description

Checks that there is at least one space (blank) or whitespace before each closing brace (`}`) for method/class/interface declarations, closure expressions and block statements.

| **Property**              | **Description**                                                                                                                                 | **Default Value** |
| --- | --- | --- |
| checkClosureMapEntryValue | If `false`, then do not check for whitespace before closing braces for closure expressions that are literal Map values, e.g. `[abc:doStuff()]`. | `true`            |
| ignoreEmptyBlock          | If `true`, then allow for `[]` in code                                                                                                          | `false`           |

Known limitations:

-   May not catch actual violations if the source line contains unicode character literals, e.g. `'\u00A0'`

Examples of violations:

``` groovy
class SomeClass { int count}                  // violation

interface SomeInterface { void doStuff()}     // violation

enum SomeEnum { OK, BAD}                      // violation

def someMethod() { return 9}                  // violation

if (ready) { doStuff()}                     // violation

if (ready) {
} else { return 9}                          // violation

for (int i=0; i<10; i++) { println i}       // violation

for (String name in names) { println name}  // violation

for (String name: names) { println name}    // violation

while (ready) { doStuff()}                  // violation

try { doStuff()}                            // violation
catch(Exception e) { logError(e)}           // violation
finally { cleanUp()}                        // violation

list.each { name -> println name}           // violation

shouldFail(Exception) { doStuff()}          // violation
```

## Further Reading

* [CodeNarc - SpaceBeforeClosingBrace](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#SpaceBeforeClosingBrace)