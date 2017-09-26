Pattern: Missing trailing comma

Issue: -

## Description

Checks whether list and map literals contain optional trailing comma. Rationale: Putting this comma in makes is easier to change the order of the elements or add new elements on the end.

| **Property** | **Description**                                                 | **Default Value** |
| --- | --- | --- |
| checkList    | To disable checking List literals, set this property to `false` | `true`            |
| checkMap     | To disable checking Map literals, set this property to `false`  | `true`            |

This is valid code:

``` groovy
  int[] array1 = [] // one line declaration
  int[] array2 = [ // empty list
             ]
  int[] array3 = [1,2,3] // one line declaration
  int[] array4 = [1,
              2,
              3, // contains trailing comma
             ]
```

Example of violations:

``` groovy
  int[] array2 = [1,
              2 // there is no trailing comma
             ]
```

## Further Reading

* [CodeNarc - TrailingComma](http://codenarc.sourceforge.net/codenarc-rules-convention.html#TrailingComma)