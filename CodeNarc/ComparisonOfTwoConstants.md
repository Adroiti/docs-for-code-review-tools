Pattern: Comparison of two constants

Issue: -

## Description

Checks for expressions where a *comparison operator* or `equals()` or `compareTo()` is used to compare two constants to each other or two literals that contain only constant values.

Here are examples of code that produces a violation:

``` groovy
23 == 67                    // violation
Boolean.FALSE != false      // violation
23 < 88                     // violation
0.17 <= 0.99                // violation
"abc" > "ddd"               // violation
[Boolean.FALSE] >= [27]     // violation
[a:1] <=> [a:2]             // violation

[1,2].equals([3,4])                                     // violation
[a:123, b:true].equals(['a':222, b:Boolean.FALSE])      // violation

[a:123, b:456].compareTo([a:222, b:567]                 // violation
[a:false, b:true].compareTo(['a':34.5, b:Boolean.TRUE]  // violation
```

## Further Reading

* [CodeNarc - ComparisonOfTwoConstants](http://codenarc.sourceforge.net/codenarc-rules-basic.html#ComparisonOfTwoConstants)