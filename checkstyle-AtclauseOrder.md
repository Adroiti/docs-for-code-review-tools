Pattern: Check the order of at-clauses

Issue: -

## Description

Checks the order of [javadoc block-tags or javadoc tags](http://docs.oracle.com/javase/8/docs/technotes/tools/windows/javadoc.html#CHDBEFIF).   
Note: Google used term "at-clauses" for block tags in his guide till 2017-02-28. 

## Examples

Default configuration 
    
    
    <module name="AtclauseOrder">
        <property name="tagOrder" value="@author, @version, @param,
        @return, @throws, @exception, @see, @since, @serial,
        @serialField, @serialData, @deprecated"/>
        <property name="target" value="CLASS_DEF, INTERFACE_DEF, ENUM_DEF,
        METHOD_DEF, CTOR_DEF, VARIABLE_DEF"/>
    </module>

## Further Reading

* [checkstyle - AtclauseOrder](http://checkstyle.sourceforge.net/config_javadoc.html#AtclauseOrder)