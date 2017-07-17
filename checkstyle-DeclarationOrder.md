Pattern: Wrong order for parts of a class or interface declaration

Issue: -

## Description

According to [Code Conventions for the Java Programming Language](http://www.oracle.com/technetwork/java/javase/documentation/codeconventions-141855.html#1852) , the parts of a class or interface declaration should appear in the following order: 

  1. Class (static) variables. First the public class variables, then protected, then package level (no access modifier), and then private. 
  2. Instance variables. First the public class variables, then protected, then package level (no access modifier), and then private. 
  3. Constructors 
  4. Methods 

Purpose of **ignore*** option is to ignore related violations, however it still impacts on other class members. 

ATTENTION: the check skips class fields which have [forward references](http://docs.oracle.com/javase/specs/jls/se8/html/jls-8.html#jls-8.3.3) from validation due to the fact that we have Checkstyle's limitations to clearly detect user intention of fields location and grouping. For example, 
    
    
    public class A {
        private double x = 1.0;
        private double y = 2.0;
        public double slope = x / y; // will be skipped from validation due to forward reference
    }
              

## Examples

To configure the check: 
    
    
    <module name="DeclarationOrder"/>
            

For example: 
    
    
                class K {
                    int a;
                    void m(){}
                    K(){}  <-- "Constructor definition in wrong order"
                    int b; <-- "Instance variable definition in wrong order"
                }
            

With **ignoreConstructors** option: 
    
    
                class K {
                    int a;
                    void m(){}
                    K(){}
                    int b; <-- "Instance variable definition in wrong order"
                }
            

With **ignoreConstructors** option and without a method definition in a source class: 
    
    
                class K {
                    int a;
                    K(){}
                    int b; <-- "Instance variable definition in wrong order"
                }

## Further Reading

* [checkstyle - DeclarationOrder](http://checkstyle.sourceforge.net/config_coding.html#DeclarationOrder)