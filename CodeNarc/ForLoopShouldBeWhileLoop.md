Pattern: Use of `for` instead of `while` loop

Issue: -

## Description

A `for` loop without an init and update statement can be simplified to a `while` loop.

Example of violations:

``` groovy
int i = 0;
for(; i < 5;) {     // Violation
    println i++
}

// These are OK
for(i in [1,2])         // OK
   println i

for(int i = 0; i<5;)    // OK
    println i++

int i = 0;
for(; i < 5; i++)       // OK
    println i

for (Plan p : plans) {  // OK
    println "Plan=$p"
}
```

## Further Reading

* [CodeNarc - ForLoopShouldBeWhileLoop](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#forloopshouldbewhileloop-rule)