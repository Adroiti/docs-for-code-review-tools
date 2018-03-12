Pattern: Code block ends with empty line

Issue: -

## Description

Checks that code blocks such as method bodies, closures and control structure bodies do not end with an empty line.

Example of violations:

``` groovy
boolean not(boolean value) {
    !value
                            // violation
}

3.times {
    println 'hello!'
                            // violation
}

for (value in []) {
    println value
                            // violation
}

for (i = 0; i < 3; i++) {
    println i
                            // violation
}

int j = 0
while (j < 3) {
  println j++
                            // violation
}

if (ready) {
    println 'ready'
                            // violation
} else {
    println 'not ready'
                            // violation
}

try {
    throw new Exception()
                            // violation
} catch (Exception e) {
    println 'exception'
                            // violation
} finally {
    println 'finally'
                            // violation
}

switch (true) {
    default:
        println 'switch'
                            // violation
}
```

## Further Reading

* [CodeNarc - BlockEndsWithBlankLine](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#BlockEndsWithBlankLine)