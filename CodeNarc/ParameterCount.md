Pattern: Method has too many parameters

Issue: -

## Description

Checks if the number of parameters in method/constructor exceeds the number of parameters specified by the `maxParameters` property.

| **Property**            | **Description**                                                   | **Default Value** |
| --- | --- | --- |
| maxParameters           | The maximum number of parameters in method/constructor            | 5                 |
| ignoreOverriddenMethods | Ignore number of parameters for methods with @Override annotation | true              |


Example of violations:

``` groovy
void someMethod(int arg1, int arg2, int arg3, int arg4, int arg5, int arg6) { // violation
}

@Override
void someMethod(int arg1, int arg2, int arg3, int arg4, int arg5, int arg6, int arg7) { // no violation if ignoreOverriddenMethods == true
}

class SampleClass {
    SampleClass(int arg1, int arg2, int arg3, int arg4, int arg5, int arg6, int arg7) { // violation
    }
}
```

## Further Reading

* [CodeNarc - ParameterCount](http://codenarc.sourceforge.net/codenarc-rules-size.html#ParameterCount)