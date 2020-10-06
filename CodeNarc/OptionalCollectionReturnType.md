Pattern: Use of `Optional` collection return type

Issue: -

## Description

Do not declare a method return type of `Optional<List>` (or `Collection`, `ArrayList`, `Set`, `Map`, `HashMap`, etc.). Return an empty collection instead.

Examples:

```groovy
class MyClass {
	Optional<Collection<Object>> getCollection() { }        // violation

	private Optional<List> getList() { }                    // violation
	Optional<ArrayList<String>> getArrayList() { }          // violation
	
	protected Optional<Set<BigDecimal>> getSet() { }        // violation
	Optional<HashSet<Boolean>> getHashSet() { }             // violation

	Optional<Map<Integer, String>> getMap() { }             // violation
	Optional<TreeMap<String, String>> getTreeMap() { }      // violation
}
```

## Further Reading

* [CodeNarc - OptionalCollectionReturnType](https://codenarc.org/codenarc-rules-design.html#optionalcollectionreturntype-rule)