Pattern: Malformed space before `{`

Issue: -

## Description

Checks that there is at least one space (blank) or whitespace before each opening brace (`{`) for method/class/interface declarations, closure expressions and block statements.

| **Property**              | **Description**                                                                                                                                 | **Default Value** |
| --- | --- | --- |
| checkClosureMapEntryValue | If `false`, then do not check for whitespace before opening braces for closure expressions that are literal Map values, e.g. `[abc:doStuff()]`. | `true`            |

Known limitations:

-   May not catch actual violations if the source line contains unicode character literals, e.g. `'\u00A0'`

Examples of violations:

``` groovy
class SomeClass{ }                            // violation
class SomeOtherClass extends AbstractClass{ } // violation

interface SomeInterface{ }                    // violation

enum SomeEnum{ OK, BAD }                      // violation

def someMethod(){ }                           // violation

if (ready){ }                               // violation

if (ready) {
} else{}                                    // violation

for (int i=0; i<10; i++){ }                 // violation

for (String name in names){ }               // violation

for (String name: names){ }                 // violation

while (ready){ }                            // violation

try{
} finally { }                               // violation

try {
} catch(Exception e){ }                     // violation

try {
} finally{ }                                // violation

list.each{ name -> }                        // violation

shouldFail(Exception){ doStuff() }          // violation
```

## Further Reading

* [CodeNarc - SpaceBeforeOpeningBrace](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#SpaceBeforeOpeningBrace)