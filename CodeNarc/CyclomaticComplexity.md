Pattern: Cyclomatic complexity is too high

Issue: -

## Description

Calculates the *Cyclomatic Complexity* for methods/classes and checks against configured threshold values.

The **maxMethodComplexity** property holds the threshold value for the cyclomatic complexity value for each method. If this value is non-zero, a method with a cyclomatic complexity value greater than this value is considered a violation.

The **maxClassAverageMethodComplexity** property holds the threshold value for the average cyclomatic complexity value for each class. If this value is non-zero, a class with an average cyclomatic complexity value greater than this value is considered a violation.

This rule treats "closure fields" as methods. If a class field is initialized to a Closure (ClosureExpression), then that Closure is analyzed and checked just like a method.

| **Property**                    | **Description**                                                                                                                                                                                                                    | **Default Value** |
| --- | --- | --- |
| maxMethodComplexity             | The maximum *cyclomatic complexity* value allowed for a single method (or "closure field"). If zero or *null*, then do not check method-level complexity.                                                                          | 20                |
| maxClassAverageMethodComplexity | The maximum average *cyclomatic complexity* value allowed for a class, calculated as the average complexity of its methods or "closure fields". If zero or *null*, then do not check average class-level complexity.               | 20                |
| maxClassComplexity              | The maximum total *cyclomatic complexity* value allowed for a class, calculated as the total complexity of its methods or "closure fields". If zero or *null*, then do not check total class-level complexity.                     | 0                 |
| ignoreMethodNames               | Specifies one or more (comma-separated) method names that that should not cause a rule violation. The names may optionally contain wildcards (\*,?). Note that the ignored methods still contribute to the class complexity value. | `null`            |

#### Cyclomatic Complexity Metric Calculation Rules<span id="Cyclomatic_Complexity_Metric_Calculation_Rules"></span>

The *cyclomatic complexity* value is calculated as follows:

*Start with a initial (default) value of one (1). Add one (1) for each occurrence of each of the following:*

-   `if` statement
-   `while` statement
-   `for` statement
-   `case` statement
-   `catch` statement
-   `&&` and `||` boolean operations
-   `?:` ternary operator and `?:` *Elvis* operator.
-   `?.` null-check operator

## Further Reading

* [CodeNarc - CyclomaticComplexity](http://codenarc.sourceforge.net/codenarc-rules-size.html#CyclomaticComplexity)