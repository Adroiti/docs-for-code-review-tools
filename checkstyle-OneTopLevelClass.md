Pattern: Top-level class not in separate source file

Issue: -

## Description

Checks that each top-level class, interface or enum resides in a source file of its own. Official description of a 'top-level' term: [7.6. Top Level Type Declarations](http://docs.oracle.com/javase/specs/jls/se7/html/jls-7.html#jls-7.6). If file doesn't contains public class, enum or interface, top-level type is the first type in file.

## Examples

An example of check's configuration: 
    
    
    <module name="OneTopLevelClass"/>
            

**ATTENTION:** This check does not support customization of validated tokens, so do not use the "tokens" property. 

An example of code with violations: 
    
    
    public class Foo{
        //methods
    }
    
    class Foo2{
        //methods
    }
            

An example of code without public top-level type: 
    
    
    class Foo{ // top-level class
        //methods
    }
    
    class Foo2{
        //methods
    }
            

An example of code without violations: 
    
    
    public class Foo{
        //methods
    }

## Further Reading

* [checkstyle - OneTopLevelClass](http://checkstyle.sourceforge.net/config_design.html#OneTopLevelClass)