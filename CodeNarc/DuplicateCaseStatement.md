Pattern: Duplicate `case` statement

Issue: -

## Description

Checks for duplicate `case` statements in a `switch` block, such as two equal integers or strings. Here are some examples of code that produces violations:

``` groovy
switch( 0 ) {
    case 1: break;
    case 2: break;
    case 2: break;          // violation
}

switch( "test" ) {
    case "$a": break;
    case "$a": break;       // ok; only flags constant values (not GStrings)
    case "ab": break;
    case "ab": break;       // violation
    case "abc": break;
}
```

## Further Reading

* [CodeNarc - DuplicateCaseStatement](http://codenarc.sourceforge.net/codenarc-rules-basic.html#DuplicateCaseStatement)