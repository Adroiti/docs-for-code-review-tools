Pattern: Restricted tokens beneath other tokens

Issue: -

## Description

Checks for restricted tokens beneath other tokens. 

WARNING: This is a very powerful and flexible check, but, at the same time, it is low-level and very implementation-dependent because its results depend on the grammar we use to build abstract syntax trees. Thus we recommend using other checks when they provide the desired functionality. Essentially, this check just works on the level of an abstract syntax tree and knows nothing about language structures. 

## Examples

Switch with no default:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="LITERAL_SWITCH"/>
        <property name="maximumDepth" value="2"/>
        <property name="limitedTokens" value="LITERAL_DEFAULT"/>
        <property name="minimumNumber" value="1"/>
    </module>
            

The condition in `for` performs no check: 
    
    
    <module name="DescendantToken">
        <property name="tokens" value="FOR_CONDITION"/>
        <property name="limitedTokens" value="EXPR"/>
        <property name="minimumNumber" value="1"/>
    </module>
            

Comparing `this` with `null` (i.e. `this == null` and `this != null`): 
    
    
    <module name="DescendantToken">
        <property name="tokens" value="EQUAL,NOT_EQUAL"/>
        <property name="limitedTokens" value="LITERAL_THIS,LITERAL_NULL"/>
        <property name="maximumNumber" value="1"/>
        <property name="maximumDepth" value="1"/>
        <property name="sumTokenCounts" value="true"/>
    </module>
            

String literal equality check:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="EQUAL,NOT_EQUAL"/>
        <property name="limitedTokens" value="STRING_LITERAL"/>
        <property name="maximumNumber" value="0"/>
        <property name="maximumDepth" value="1"/>
    </module>
            

Assert statement may have side effects (formatted for browser display): 
    
    
    <module name="DescendantToken">
        <property name="tokens" value="LITERAL_ASSERT"/>
        <property name="limitedTokens" value="ASSIGN,DEC,INC,POST_DEC,
            POST_INC,PLUS_ASSIGN,MINUS_ASSIGN,STAR_ASSIGN,DIV_ASSIGN,MOD_ASSIGN,
            BSR_ASSIGN,SR_ASSIGN,SL_ASSIGN,BAND_ASSIGN,BXOR_ASSIGN,BOR_ASSIGN,
            METHOD_CALL"/>
        <property name="maximumNumber" value="0"/>
    </module>
            

The initialiser in `for` performs no setup (where a `while` statement could be used instead): 
    
    
    <module name="DescendantToken">
        <property name="tokens" value="FOR_INIT"/>
        <property name="limitedTokens" value="EXPR"/>
        <property name="minimumNumber" value="1"/>
    </module>
            

A switch within a switch: 
    
    
    <module name="DescendantToken">
        <property name="tokens" value="LITERAL_SWITCH"/>
        <property name="limitedTokens" value="LITERAL_SWITCH"/>
        <property name="maximumNumber" value="0"/>
        <property name="minimumDepth" value="1"/>
    </module>
            

A return statement from within a catch or finally block:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="LITERAL_FINALLY,LITERAL_CATCH"/>
        <property name="limitedTokens" value="LITERAL_RETURN"/>
        <property name="maximumNumber" value="0"/>
    </module>
            

A try statement within a catch or finally block:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="LITERAL_CATCH,LITERAL_FINALLY"/>
        <property name="limitedTokens" value="LITERAL_TRY"/>
        <property name="maximumNumber" value="0"/>
    </module>
            

Too many cases within a switch:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="LITERAL_SWITCH"/>
        <property name="limitedTokens" value="LITERAL_CASE"/>
        <property name="maximumDepth" value="2"/>
        <property name="maximumNumber" value="10"/>
    </module>
            

Too many local variables within a method:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="METHOD_DEF"/>
        <property name="limitedTokens" value="VARIABLE_DEF"/>
        <property name="maximumDepth" value="2"/>
        <property name="maximumNumber" value="10"/>
    </module>
            

Too many returns from within a method:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="METHOD_DEF"/>
        <property name="limitedTokens" value="LITERAL_RETURN"/>
        <property name="maximumNumber" value="3"/>
    </module>
            

Too many fields within an interface:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="INTERFACE_DEF"/>
        <property name="limitedTokens" value="VARIABLE_DEF"/>
        <property name="maximumDepth" value="2"/>
        <property name="maximumNumber" value="0"/>
    </module>
            

Limits the number of exceptions a method can throw:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="LITERAL_THROWS"/>
        <property name="limitedTokens" value="IDENT"/>
        <property name="maximumNumber" value="1"/>
    </module>
            

Limits the number of expressions in a method:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="METHOD_DEF"/>
        <property name="limitedTokens" value="EXPR"/>
        <property name="maximumNumber" value="200"/>
    </module>
            

Disallows empty statements:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="EMPTY_STAT"/>
        <property name="limitedTokens" value="EMPTY_STAT"/>
        <property name="maximumNumber" value="0"/>
        <property name="maximumDepth" value="0"/>
        <property name="maximumMessage"
            value="Empty statement is not allowed."/>
    </module>
            

Too many fields within a class:
    
    
    <module name="DescendantToken">
        <property name="tokens" value="CLASS_DEF"/>
        <property name="limitedTokens" value="VARIABLE_DEF"/>
        <property name="maximumDepth" value="2"/>
        <property name="maximumNumber" value="10"/>
    </module>

## Further Reading

* [checkstyle - DescendantToken](http://checkstyle.sourceforge.net/config_misc.html#DescendantToken)