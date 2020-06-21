Pattern: Unnecessary `null` check

Issue: -

## Description

Groovy contains the `safe` dereference operator. It can be used in boolean conditional statements to safely replace explicit `x == null` tests. Also, testing the `this` or `super` reference for null equality is pointless and can be removed.

Examples of violations:

``` groovy
if (obj != null && obj.method()) { }

if (obj != null && obj.prop) { }

// this is pointless and won't avoid NullPointerException
if (obj.method() && obj != null ) { }

if (this == null) { }
if (null == this) { }
if (this != null) { }
if (null != this) { }

if (super == null) { }
if (null == super) { }
if (super != null) { }
if (null != super) { }
```

Examples of acceptable code:

``` groovy
// null check it OK
if (obj != null) { }

// null safe dereference in if is OK
if (obj?.method()) { }

// null safe dereference in ternary is OK
(obj?.prop && obj?.prop2) ? x : y

// obj is reused in a parameter list, so OK
if (obj != null && obj.method() && isValid(obj)) { }

// rule is not so complex yet...
(obj != null && obj.prop && obj.method()) ? x : y
```

## Further Reading

* [CodeNarc - UnnecessaryNullCheck](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessarynullcheck-rule)