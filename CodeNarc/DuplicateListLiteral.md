Pattern: Duplicate list literal

Issue: -

## Description

This rule checks for duplicate *List* literals within the current class. This rule only checks for *List*s where values are all constants or literals.

List literals within annotations are ignored.

Code containing duplicate *List* literals can usually be improved by declaring the *List* as a constant field.

By default, the rule does not analyze test files. This rule sets the default value of the *doNotApplyToFilesMatching* property to ignore file names ending in 'Test.groovy', 'Tests.groovy' or 'TestCase.groovy'.

Examples of violations:

``` groovy
  def var1 = [1, null, Boolean.FALSE, 'x', true]
  def var2 = [1, null, Boolean.FALSE, 'x', true]        // violation

  def var1 = [1, [3, 4]]
  def var2 = [1, [3,4]]     // violation

  def var1 = [123, [3, 4, [x:99], 5]]
  def var2 = [99, [3, 4, [x:99], 5]]        // violation [3, 4, [x:99], 5]
```

Examples of non-violations:

``` groovy
def name
def var1 = [name, 'b', 'c']
def var2 = [name, 'b', 'c']   // not a violation; name is a variable

def var1 = [1, 7+5]
def var2 = [1, 7+5]      // not a violation; contains a non-constant/literal expression
```

You can suppress the error by annotating a class or method with the `@SuppressWarnings('DuplicateListLiteral')` annotation.

## Further Reading

* [CodeNarc - DuplicateListLiteral](https://codenarc.github.io/CodeNarc/codenarc-rules-dry.html#duplicatelistliteral-rule)