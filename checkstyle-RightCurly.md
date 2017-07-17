Pattern: Wrong `}` placement

Issue: -

## Description

Checks the placement of right curly braces (`'}'`) for if-else, try-catch-finally blocks, while-loops, for-loops, method definitions, class definitions, constructor definitions, instance and static initialization blocks. The policy to verify is specified using the property `option`. 

## Examples

To configure the check: 
    
    
    <module name="RightCurly"/>
            

To configure the check with policy `alone` for `else` and [METHOD_DEF](http://checkstyle.sourceforge.net/apidocs/com/puppycrawl/tools/checkstyle/api/TokenTypes.html#METHOD_DEF) tokens: 
    
    
    <module name="RightCurly">
        <property name="option" value="alone"/>
        <property name="tokens" value="LITERAL_ELSE, METHOD_DEF"/>
    </module>

## Further Reading

* [checkstyle - RightCurly](http://checkstyle.sourceforge.net/config_blocks.html#RightCurly)