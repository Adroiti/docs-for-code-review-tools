Pattern: Specify what warnings SuppressWarnings is not allowed to suppress

Issue: -

## Description

This check allows you to specify what warnings that SuppressWarnings is not allowed to suppress. You can also specify a list of TokenTypes that the configured warning(s) cannot be suppressed on.

Limitations: This check does not consider conditionals inside the SuppressWarnings annotation.   
For example: @SuppressWarnings((false) ? (true) ? "unchecked" : "foo" : "unused") According to the above example, the "unused" warning is being suppressed not the "unchecked" or "foo" warnings. All of these warnings will be considered and matched against regardless of what the conditional evaluates to.   
The check also does not support code like `@SuppressWarnings("un" \+ "used")`, `@SuppressWarnings((String) "unused")` or `@SuppressWarnings({('u' + (char)'n') + (""+("used" \+ (String)"")),})`. 

## Examples

To configure the check:
    
    
     <module name="SuppressWarnings"/>
            

To configure the check so that the "unchecked" and "unused" warnings cannot be suppressed on anything but variable and parameter declarations. 
    
    
       <module name="SuppressWarnings">
          <property name="format"
              value="^unchecked$|^unused$"/>
          <property name="tokens"
              value="
              CLASS_DEF,INTERFACE_DEF,ENUM_DEF,
              ANNOTATION_DEF,ANNOTATION_FIELD_DEF,
              ENUM_CONSTANT_DEF,METHOD_DEF,CTOR_DEF
              "/>
       </module>

## Further Reading

* [checkstyle - SuppressWarnings](http://checkstyle.sourceforge.net/config_annotation.html#SuppressWarnings)