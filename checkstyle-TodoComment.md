Pattern: TODO comments

Issue: -

## Description

A check for `TODO:` comments. Actually it is a generic [regular expression](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html) matcher on Java comments. To check for other patterns in Java comments, set the `format` property. 

## Examples

To configure the check: 
    
    
    <module name="TodoComment"/>
            

To configure the check for comments that contain `TODO` and `FIXME`: 
    
    
    <module name="TodoComment">
        <property name="format" value="(TODO)|(FIXME)"/>
    </module>

## Further Reading

* [checkstyle - TodoComment](http://checkstyle.sourceforge.net/config_misc.html#TodoComment)