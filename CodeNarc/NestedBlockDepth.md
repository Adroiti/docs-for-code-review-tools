Pattern: Too many nested blocks

Issue: -

## Description

Checks for blocks or closures nested more deeply than a configured maximum number. Blocks include `if`, `for`, `while`, `switch`, `try`, `catch`, `finally` and `synchronized` blocks/statements, as well as closures.

Methods calls, constructor calls, and property access through Builder objects are ignore. For instance, this code does not cause a violation:

``` groovy
someBuilder.root {
    foo {
        bar {
            baz {
                quix {
                    qux {
                        quaxz {
                        }
                    }
                }
            }
        }
    }
}
```

| **Property**        | **Description**                                                                                                                                                                                      | **Default Value** |
| --- | --- | --- |
| maxNestedBlockDepth | The maximum number of nesting levels. A block or closure nested deeper than that number of levels is considered a violation.                                                                         | 5                 |
| ignoreRegex         | Determines what is a builder call. | .\*(b             |

## Further Reading

* [CodeNarc - NestedBlockDepth](https://codenarc.github.io/CodeNarc/codenarc-rules-size.html#nestedblockdepth-rule)