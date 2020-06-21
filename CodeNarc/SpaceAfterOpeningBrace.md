Pattern: Malformed space after `{`

Issue: -

## Description

Checks that there is at least one space (blank) or whitespace after each opening brace (`{`) for method/class/interface declarations, closure expressions and block statements.

| **Property**              | **Description**                                                                                                                                | **Default Value** |
| --- | --- | --- |
| checkClosureMapEntryValue | If `false`, then do not check for whitespace after opening braces for closure expressions that are literal Map values, e.g. `[abc:doStuff()]`. | `true`            |
| ignoreEmptyBlock          | If `true`, then allow for `[]` in code                                                                                                         | `false`           |

Examples of violations:

``` groovy
class SomeClass{int count }                   // violation

interface SomeInterface {static final OK = 1 }// violation

enum SomeEnum {OK, BAD }                      // violation

def someMethod() {int count }                 // violation

if (ready) {println 9 }                     // violation

if (ready) {
} else {println 99}                         // violation

for (int i=0; i<10; i++) {println i }       // violation

for (String name in names) {println name }  // violation

for (String name: names) {println name }    // violation

while (ready) {println time }               // violation

try {doStuff()                              // violation
} catch(Exception e) {x=77 }                // violation
} finally {println 'error' }                // violation

list.each {name -> }                        // violation

shouldFail(Exception) {doStuff() }          // violation
```

## Further Reading

* [CodeNarc - SpaceAfterOpeningBrace](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#spaceafteropeningbrace-rule)