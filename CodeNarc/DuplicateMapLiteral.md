Pattern: Duplicate map literal

Issue: -

## Description

This rule checks for duplicate *Map* literals within the current class. This rule only checks for *Map*s where the keys and values are all constants or literals.

Code containing duplicate *Map* literals can usually be improved by declaring the *Map* as a constant field.

By default, the rule does not analyze test files. This rule sets the default value of the *doNotApplyToFilesMatching* property to ignore file names ending in 'Test.groovy', 'Tests.groovy' or 'TestCase.groovy'.

Examples of violations:

``` groovy
  def var1 = [a:1, b:null, c:Boolean.FALSE, d:'x', e:true]
  def var2 = [a:1, b:null, c:Boolean.FALSE, d:'x', e:true]      // violation

  def var1 = [a:1, b:[x:3,y:4]]
  def var2 = [a:1, b:[x:3,y:4]]     // violation

  def var1 = [a:1, b:[3,4]]
  def var2 = [a:1, b:[3,4]]     // violation

  def var1 = [null:1, 'b':2, (Boolean.FALSE):3, (4):4, (true):5]
  def var2 = [null:1, 'b':2, (Boolean.FALSE):3, (4):4, (true):5]    // violation
```

Examples of non-violations:

``` groovy
def name
def var1 = [(name):1, b:1, c:1]
def var2 = [(name):1, b:1, c:1]   // not a violation; name is a variable

def var1 = [a:1, b:['x', name]]
def var2 = [a:1, b:['x', name]]   // not a violation; name is a variable

def var1 = [a:7+5]
def var2 = [a:7+5]      // not a violation; contains a non-constant/literal expression
```

You can suppress the error by annotating a class or method with the `@SuppressWarnings('DuplicateMapLiteral')` annotation.

## Further Reading

* [CodeNarc - DuplicateMapLiteral](http://codenarc.sourceforge.net/codenarc-rules-dry.html#DuplicateMapLiteral)