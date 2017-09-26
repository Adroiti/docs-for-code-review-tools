Pattern: Malformed space after `{`

Issue: -

## Description

Check that there is at least one space (blank) or whitespace after each opening brace ("{") for method/class/interface declarations, closure expressions and block statements.

| **Property**              | **Description**                                                                                                                                | **Default Value** |
| --- | --- | --- |
| checkClosureMapEntryValue | If `false`, then do not check for whitespace after opening braces for closure expressions that are literal Map values, e.g. `[abc:doStuff()]`. | `true`            |
| ignoreEmptyBlock          | If `true`, then allow for `[]` in code                                                                                                         | `false`           |

Examples of violations:

``` groovy
class MyClass{int count }                   // violation

interface MyInterface {static final OK = 1 }// violation

enum MyEnum {OK, BAD }                      // violation

def myMethod() {int count }                 // violation

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

* [CodeNarc - SpaceAfterOpeningBrace](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#SpaceAfterOpeningBrace)