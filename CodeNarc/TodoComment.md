Pattern: Unresolved warning comment

Issue: -

## Description

Developers often add comments to code which is not complete or needs review. Most likely you want to fix or review the code, and then remove the comment, before you consider the code to be production ready.

## Default configuration

```xml
<rule class='org.codenarc.rule.generic.IllegalRegexRule'>
  <property name='name' value='TodoComment'/>
  <property name='regex' value='(TODO)|(FIXME)'/>
  <property name='violationMessage' value='Resolve unexpected comment.'/>
</rule>
```

## Examples

Example of **incorrect** code:

```groovy
// FIXME: this is not a good idea
// TODO: need code review
doSomethingExperimental();
```

Example of **correct** code:

```groovy
// NOT READY FOR PRIME TIME
// but too bad, it is not a predefined warning term
doSomethingExperimental();
```


## Further Reading

* [checkstyle - IllegalRegex](https://codenarc.github.io/CodeNarc/codenarc-rules-generic.html#illegalregex-rule)
