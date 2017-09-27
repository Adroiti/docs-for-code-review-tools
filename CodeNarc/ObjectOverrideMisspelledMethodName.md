Pattern: Misspelled override method name

Issue: -

## Description

Verifies that the names of the most commonly overridden methods of `Object`: `equals`, `hashCode` and `toString`, are correct.

Here are some examples of code that produces violations:

``` groovy
boolean equal(Object o) {}                  // violation
boolean equal(int other) {}                 // ok; wrong param type
boolean equal(Object o, int other) {}       // ok; too many params

boolean equaLS(Object o) {}                 // violation

int hashcode() {}                           // violation
int hashCOde() {}                           // violation
int hashcode(int value) {}                  // ok; not empty params

String tostring() {}                        // violation
String toSTring() {}                        // violation
String tostring(int value) {}               // ok; not empty params
```

## Further Reading

* [CodeNarc - ObjectOverrideMisspelledMethodName](http://codenarc.sourceforge.net/codenarc-rules-naming.html#ObjectOverrideMisspelledMethodName)