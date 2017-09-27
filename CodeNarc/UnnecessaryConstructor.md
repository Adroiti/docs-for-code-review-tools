Pattern: Unnecessary constructor

Issue: -

## Description

This rule detects when a constructor is not necessary; i.e., when there's only one constructor, it's `public`, has an empty body, and takes no arguments, or else contains only a single call to `super()`.

| **Property**      | **Description**                                                                        | **Default Value** |
| --- | --- | --- |
| ignoreAnnotations | If `true`, then do not report violations if a constructor has one or more annotations. | false             |

Example of violations:

``` groovy
class SomeClass {
    public SomeClass() {          // violation; constructor is not necessary
    }
}

class SomeClass2 extends OtherClass {
    SomeClass2() {                // violation; constructor is not necessary
        super()
    }
}
```

## Further Reading

* [CodeNarc - UnnecessaryConstructor](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryConstructor)