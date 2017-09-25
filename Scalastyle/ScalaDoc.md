Pattern: Malformed Scaladoc

Issue: -

## Description

It is important to provide documentation for all packages, classes, traits, methods, and other members. Scaladoc generally follows the conventions of Javadoc, however there are many additional features to make writing scaladoc simpler.

In general, you want to worry more about substance and writing style than in formatting. Scaladocs need to be useful to new users of the code as well as experienced users. 

## Parameters
<table><tr><th>Name</th><th>Description</th><th>Type</th><th>Default Value</th></tr><tr><td>ignoreRegex</td>
        <td>Regular expression</td>
        <td>string</td>
        <td>^$</td>
      </tr><tr><td>ignoreTokenTypes</td>
        <td>Comma Separated String</td>
        <td>string</td>
        <td>^$</td>
      </tr><tr><td>ignoreOverride</td>
        <td>Ignore override</td>
        <td>boolean</td>
        <td>false</td>
      </tr><tr><td>indentStyle</td>
        <td>Force indent style</td>
        <td>string</td>
        <td>anydoc</td>
      </tr></table>
	  

Ignore tokens is a comma separated string that may include the following : `PatDefOrDcl` (variables), `TmplDef` (classes, traits), `TypeDefOrDcl` (type definitions), `FunDefOrDcl` (functions). Supported indentation styles are `scaladoc` (for Scaladoc-style comments, with two spaces before the asterisk), `javadoc` (for JavaDoc-style comments, with a single space before the asterisk) or `anydoc` to support any style (any number of spaces before the asterisk). For backwards compatibility, if left empty, `anydoc` will be assumed.

## Example configuration

```xml
<check enabled="true" class="org.scalastyle.scalariform.ScalaDocChecker" level="warning">
 <parameters>
  <parameter name="ignoreRegex">(.*Spec$)|(.*SpecIT$)</parameter>
  <parameter name="ignoreTokenTypes">PatDefOrDcl,TypeDefOrDcl,FunDefOrDcl,TmplDef</parameter>
  <parameter name="ignoreOverride">false</parameter>
  <parameter name="indentStyle">anydoc</parameter>
 </parameters>
</check>
```
<a name="org_scalastyle_scalariform_SimplifyBooleanExpressionChecker" />

## Further Reading

* [Scalastyle - ScalaDoc](http://www.scalastyle.org/rules-1.0.0.html#org_scalastyle_scalariform_ScalaDocChecker)