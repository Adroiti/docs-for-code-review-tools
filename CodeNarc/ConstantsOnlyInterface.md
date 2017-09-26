Pattern: Interface with constants only

Issue: -

## Description

An interface should be used only to model a behaviour of a class: using an interface as a container of constants is a poor usage pattern. Example:

``` groovy
public interface ConstantsInterface {
    public static final int CONSTANT_1 = 0
    public static final String CONSTANT_2 = "1"
}
```

## Further Reading

* [CodeNarc - ConstantsOnlyInterface](http://codenarc.sourceforge.net/codenarc-rules-design.html#ConstantsOnlyInterface)