Pattern: Avoid escaped unicode characters

Issue: -

## Description

Restrict using [Unicode escapes](http://docs.oracle.com/javase/specs/jls/se7/html/jls-3.html#jls-3.3) (e.g. \u221e). It is possible to allow using escapes for [non-printable(control) characters](https://en.wiktionary.org/wiki/Appendix:Control_characters). Also, this check can be configured to allow using escapes if trail comment is present. By the option it is possible to allow using escapes if literal contains only them. 

## Examples

Examples of using Unicode: 
    
    
    String unitAbbrev = "μs"; //Best: perfectly clear even without a comment.
    String unitAbbrev = "\u03bcs"; //Poor: the reader has no idea what this is.
            

An example of how to configure the check is: 
    
    
    <module name="AvoidEscapedUnicodeCharacters"/>
            

An example of non-printable(control) characters. 
    
    
    return '\ufeff' + content; // byte order mark
            

An example of how to configure the check to allow using escapes for non-printable(control) characters: 
    
    
    <module name="AvoidEscapedUnicodeCharacters">
        <property name="allowEscapesForControlCharacters" value="true"/>
    </module>
            

Example of using escapes with trail comment: 
    
    
    String unitAbbrev = "\u03bcs"; // Greek letter mu, "s"
            

An example of how to configure the check to allow using escapes if trail comment is present: 
    
    
    <module name="AvoidEscapedUnicodeCharacters">
        <property name="allowByTailComment" value="true"/>
    </module>
            

Example of using escapes if literal contains only them: 
    
    
    String unitAbbrev = "\u03bc\u03bc\u03bc";
            

An example of how to configure the check to allow escapes if literal contains only them: 
    
    
    <module name="AvoidEscapedUnicodeCharacters">
        <property name="allowIfAllCharactersEscaped" value="true"/>
    </module>
            

An example of how to configure the check to allow non-printable escapes: 
    
    
    <module name="AvoidEscapedUnicodeCharacters">
        <property name="allowNonPrintableEscapes" value="true"/>
    </module>

## Further Reading

* [checkstyle - AvoidEscapedUnicodeCharacters](http://checkstyle.sourceforge.net/config_misc.html#AvoidEscapedUnicodeCharacters)