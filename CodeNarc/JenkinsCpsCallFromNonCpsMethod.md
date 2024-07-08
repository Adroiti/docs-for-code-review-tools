Pattern: CPS transformed method may not be called

Issue: -

## Description

CPS transformed methods may not be called from non CPS transformed methods in Jenkins. Every analyzed Method is assumed to be CPS transformed, except it is annotated with `com.cloudbees.groovy.cps.NonCPS`, is a constructor or a library method that is not configured in cpsPackages. Pipeline steps are assumed to be CPS transformed except for ‘echo’, ‘properties’ and ‘getContext’.

Known limitations:

    Methods are only checked for their name, parameters are ignored. Therefore false positives are possible if two overloaded methods are both CPS and non CPS transformed respectively.
    Because of their dynamic nature, pipeline steps can only be recognized if they are called on a predefined script variable (default is script).
    Method calls on dynamic types (Object) can’t be resolved.


## Examples

```groovy
class SomeClass() {
    public int value = cpsMethod() // Violation
    SomeClass() {}
}

@NonCPS
void nonCpsMethod() {}

void cpsMethod() {}

@NonCPS
void someMethod() {
    nonCpsMethod() // OK
    new SomeClass() // OK
    cpsMethod() // Violation
    script.sh('echo hello') // Violation
}
```

## Further Reading

* [CodeNarc - CpsCallFromNonCpsMethod](https://codenarc.org/codenarc-rules-jenkins.html#cpscallfromnoncpsmethod-rule)