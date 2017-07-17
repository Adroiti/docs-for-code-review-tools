Pattern: Malformed Javadoc comment

Issue: -

## Description

Validates Javadoc comments to help ensure they are well formed. The following checks are performed: 

  - Ensures the first sentence ends with proper punctuation (That is a period, question mark, or exclamation mark, by default). Javadoc automatically places the first sentence in the method summary table and index. Without proper punctuation the Javadoc may be malformed. All items eligible for the `{@inheritDoc}` tag are exempt from this requirement. 
  - check text for Javadoc statements that do not have any description. This includes both completely empty Javadoc, and Javadoc with only tags such as `@param` and `@return`. 
  - check text for incomplete HTML tags. Verifies that HTML tags have corresponding end tags and issues an "Unclosed HTML tag found:" error if not. An "Extra HTML tag found:" error is issued if an end tag is found without a previous open tag. 
  - check that a package Javadoc comment is well-formed (as described above) and NOT missing from any package-info.java files. 
  - check for allowed HTML tags. The list of allowed HTML tags is "a", "abbr", "acronym", "address", "area", "b", "bdo", "big", "blockquote", "br", "caption", "cite", "code", "colgroup", "dd", "del", "div", "dfn", "dl", "dt", "em", "fieldset", "font", "h1" to "h6", "hr", "i", "img", "ins", "kbd", "li", "ol", "p", "pre", "q", "samp", "small", "span", "strong", "sub", "sup", "table", "tbody", "td", "tfoot", "th", "thread", "tr", "tt", "u", "ul". 

These checks were patterned after the checks made by the [DocCheck](http://maven-doccheck.sourceforge.net/) doclet available from Sun. Note: Original Sun's DocCheck tool does not exist anymore. 

## Examples

To configure the default check: 
    
    
    <module name="JavadocStyle"/>
            

To configure the check for `public` scope: 
    
    
    <module name="JavadocStyle">
       <property name="scope" value="public"/>
    </module>
            

To configure the check for Javadoc which is in `private`, but not in `package` scope: 
    
    
    <module name="JavadocStyle">
       <property name="scope" value="private"/>
       <property name="excludeScope" value="package"/>
    </module>
            

To configure the check to turn off first sentence checking: 
    
    
    <module name="JavadocStyle">
       <property name="checkFirstSentence" value="false"/>
    </module>

## Further Reading

* [checkstyle - JavadocStyle](http://checkstyle.sourceforge.net/config_javadoc.html#JavadocStyle)