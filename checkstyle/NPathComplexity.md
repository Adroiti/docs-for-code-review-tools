Pattern: NPath complexity is too high

Issue: -

## Description

The NPATH metric computes the number of possible execution paths through a function(method). It takes into account the nesting of conditional statements and multi-part boolean expressions (A && B, C || D, E ? F :G and their combinations).

Metric was described at "[NPATH: a measure of execution pathcomplexity and its applications"](http://dl.acm.org/citation.cfm?id=42379). If you need detailed description of algorithm, please read that article, it is well written and have number of examples and details. 

Here is some quotes:

> An NPATH threshold value of 200 has been established for a function. The value 200 is based on studies done at AT&T Bell Laboratories [1988 year]. 

> Some of the most effective methods of reducing the NPATH value include  
\- distributing functionality,  
\- implementing multiple if statements as a switch statement  
\- creating a separate function for logical expressions with a high count of and (&&) and or (||) operators. 

> Although strategies to reduce the NPATH complexity of functions are important, care must be taken not to distort the logical clarity of the software by applying a strategy to reduce the complexity of functions. That is, there is a point of diminishing return beyond which a further attempt at reduction of complexity distorts the logical clarity of the system structure. 

**Rationale:** Nejmeh says that his group had an informal NPATH limit of 200 on individual routines; functions(methods) that exceeded this value were candidates for further decomposition - or at least a closer look. **Please do not be fanatic with limit 200** \- choose number that suites your project style. Limit 200 is empirical number base on some sources of at AT&T Bell Laboratories of 1988 year. 

## Examples

To configure the check: 


```xml
<module name="NPathComplexity"/>
```
        

To configure the check with a threshold of 1000: 


```xml
<module name="NPathComplexity">
    <property name="max" value="1000"/>
</module>
```

## Further Reading

* [checkstyle - NPathComplexity](http://checkstyle.sourceforge.net/config_metrics.html#NPathComplexity)
