Pattern: Malformed whitespace around `<` or `>`

Issue: -

## Description

Checks that the whitespace around the Generic tokens (angle brackets) `<` and `>` are correct to the _typical_ convention. The convention is not configurable. 

Left angle bracket (`<`): 

  - should be preceded with whitespace only in generic methods definitions.
  - should not be preceded with whitespace when it is precede method name or following type name.
  - should not be followed with whitespace in all cases.

Right angle bracket (`>`): 

  - should not be preceded with whitespace in all cases.
  - should be followed with whitespace in almost all cases, except diamond operators and when preceding method name.

Examples with correct spacing: 


```java
public void <K, V extends Number> boolean foo(K, V) {} // Generic methods definitions
class name<T1, T2, ..., Tn> {}            // Generic type definition
OrderedPair<String, Box<Integer>> p;      // Generic type reference
boolean same = Util.<Integer, String>compare(p1, p2);  // Generic preceded method name
Pair<Integer, String> p1 = new Pair<>(1, "apple");     // Diamond operator
List<T> list = ImmutableList.Builder<T>::new;          // Method reference
sort(list, Comparable::<String>compareTo);// Method reference
```
        

## Examples

To configure the check: 


```xml
<module name="GenericWhitespace"/>
```

## Further Reading

* [checkstyle - GenericWhitespace](https://checkstyle.sourceforge.io/checks/whitespace/genericwhitespace.html#GenericWhitespace)
