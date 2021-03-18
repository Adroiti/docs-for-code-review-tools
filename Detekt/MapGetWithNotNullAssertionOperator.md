Pattern: Use of `map[]`/`map.get()` with `!!`

Issue: -

## Description

Reports calls of the map access methods `map[]` or `map.get()` with a not-null assertion operator `!!`. This may result in a `NullPointerException`. Preferred access methods are `map[]` without `!!`, `map.getValue()`, `map.getOrDefault()` or `map.getOrElse()`.

Example of **incorrect** code:

```kotlin val map = emptyMap<String, String>() map["key"]!!
 val map = emptyMap<String, String>() map.get("key")!!```

Example of **correct** code:

```kotlinval map = emptyMap<String, String>()map["key"]
val map = emptyMap<String, String>()map.getValue("key")
val map = emptyMap<String, String>()map.getOrDefault("key", "")
val map = emptyMap<String, String>()map.getOrElse("key", { "" })```

## Further Reading

* [Detekt - MapGetWithNotNullAssertionOperator](https://detekt.github.io/detekt/potential-bugs.html#mapgetwithnotnullassertionoperator)