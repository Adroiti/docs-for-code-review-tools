Pattern: Unnecessary `def` in variable declaration

Issue: -

## Description

If a variable has a visibility modifier or a type declaration, then the `def` keyword is unneeded. For instance `def private n = 2` is redundant and can be simplified to `private n = 2`.

Examples of violations:

``` groovy
// def and private is redundant
def private string1 = 'example'

// def and protected is redundant
def protected string2 = 'example'

// def and public is redundant
def public string3 = 'example'

// def and static is redundant
def static string4 = 'example'

// def and final is redundant
def final string5 = 'example'

// def and a type is redundant
def String string6 = 'example'
```

## Further Reading

* [CodeNarc - UnnecessaryDefInVariableDeclaration](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryDefInVariableDeclaration)