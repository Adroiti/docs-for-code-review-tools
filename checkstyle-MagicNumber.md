Pattern: Magic numbers

Issue: -

## Description

Checks that there are no [ "magic numbers"](https://en.wikipedia.org/wiki/Magic_number_%28programming%29) where a magic number is a numeric literal that is not defined as a constant. By default, -1, 0, 1, and 2 are not considered to be magic numbers. 

It is fine to have one constant defining multiple numeric literals within one expression: 
    
    
    static final int SECONDS_PER_DAY = 24 * 60 * 60;
    static final double SPECIAL_RATIO = 4.0 / 3.0;
    static final double SPECIAL_SUM = 1 + Math.E;
    static final double SPECIAL_DIFFERENCE = 4 - Math.PI;
    static final Border STANDARD_BORDER = BorderFactory.createEmptyBorder(3, 3, 3, 3);
    static final Integer ANSWER_TO_THE_ULTIMATE_QUESTION_OF_LIFE = new Integer(42);
              

## Examples

To configure the check with default configuration: 
    
    
    <module name="MagicNumber"/>
            

results is following violations: 
    
    
    @MyAnnotation(6) // violation
    class MyClass {
        private field = 7; // violation
    
        void foo() {
           int i = i + 1; // no violation
           int j = j + 8; // violation
        }
    }
            

To configure the check so that it checks floating-point numbers that are not 0, 0.5, or 1: 
    
    
    <module name="MagicNumber">
        <property name="tokens" value="NUM_DOUBLE, NUM_FLOAT"/>
        <property name="ignoreNumbers" value="0, 0.5, 1"/>
        <property name="ignoreFieldDeclaration" value="true"/>
        <property name="ignoreAnnotation" value="true"/>
    </module>
            

results is following violations: 
    
    
    @MyAnnotation(6) // no violation
    class MyClass {
        private field = 7; // no violation
    
        void foo() {
           int i = i + 1; // no violation
           int j = j + 8; // violation
        }
    }
            

Config Example for constantWaiverParentToken Option: 
    
    
            <module name="MagicNumber">
                <property name="constantWaiverParentToken" value="ASSIGN,ARRAY_INIT,EXPR,
                UNARY_PLUS, UNARY_MINUS, TYPECAST, ELIST, DIV, PLUS "/>
            </module>
            

result is following violation:
    
    
       class TestMethodCall {
          public void method2() {
               final TestMethodCall dummyObject = new TestMethodCall(62);    //violation
               final int a = 3;        // ok as waiver is ASSIGN
               final int [] b = {4, 5} // ok as waiver is ARRAY_INIT
               final int c = -3;       // ok as waiver is UNARY_MINUS
               final int d = +4;       // ok as waiver is UNARY_PLUS
               final int e = method(1, 2) // ELIST is there but violation due to METHOD_CALL
               final int x = 3 * 4;    // violation
               final int y = 3 / 4;    // ok as waiver is DIV
               final int z = 3 + 4;    // ok as waiver is PLUS
               final int w = 3 - 4;    // violation
               final int x = (int)(3.4);    //ok as waiver is TYPECAST
          }
       }

## Further Reading

* [checkstyle - MagicNumber](http://checkstyle.sourceforge.net/config_coding.html#MagicNumber)