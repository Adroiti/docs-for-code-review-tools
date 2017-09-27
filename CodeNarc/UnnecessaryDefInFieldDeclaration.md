Pattern: Unnecessary `def` in field declaration

Issue: -

## Description

If a field has a visibility modifier or a type declaration, then the `def` keyword is unneeded. For instance, `static def constraints = <span id="a"></span>` is redundant and can be simplified to `static constraints = <span id="a"></span>`.

Example of violations:

``` groovy
class MyClass {
    // def is redundant
    static def constraints = {  }

    // def and private is redundant
    def private field1 = { }

    // def and protected is redundant
    def protected field2 = { }

    // def and public is redundant
    def public field3 = { }

    // def and static is redundant
    def static field4 = { }

    // def and type is redundant
    def Object field5 = { }
}
```

## Further Reading

* [CodeNarc - UnnecessaryDefInFieldDeclaration](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryDefInFieldDeclaration)