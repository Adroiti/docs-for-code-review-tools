Pattern: Assignment in conditional

Issue: -

## Description

An assignment operator (`=`) was used in a conditional test. This is usually a typo, and the comparison operator (`==`) was intended.

Example of violations:

``` groovy
if ((value = true)) {
    // should be ==
}

while (value = true) {
    // should be ==
}

(value = true) ? x : y
(value = true) ?: x

// the following code has no violations
if (value == true) {
}

value == true ? x : y
value == true ?: x
```

## Further Reading

* [CodeNarc - AssignmentInConditional](http://codenarc.sourceforge.net/codenarc-rules-basic.html#AssignmentInConditional)