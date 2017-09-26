Pattern: Use of deprecated `groovy.lang.Immutable`

Issue: -

## Description

The `groovy.lang.Immutable` annotation has been deprecated and replaced by `groovy.transform.Immutable`. Do not use the `Immutable` in `groovy.lang`.

Example of violations:

``` groovy
@Immutable                          // Violation (no import means groovy.lang.Immutable)
class Person { }

@groovy.lang.Immutable              // Violation
class Person { }

import groovy.lang.Immutable as Imtl
@Imtl                               // Violation
class Person { }
```

Example of valid use of @Immutable:

``` groovy
@groovy.transform.Immutable                 // OK
class Person { }

import groovy.transform.Immutable           // OK
@Immutable
class Person { }

import groovy.transform.*
@Immutable                                  // OK
class Person { }

import groovy.transform.Immutable as Imtl
@Imtl                                       // OK
class Person { }

@javax.annotation.concurrent.Immutable      // OK
class MyClass { }
```

## Further Reading

* [CodeNarc - GroovyLangImmutable](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#GroovyLangImmutable)