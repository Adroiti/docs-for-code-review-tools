Pattern: Enforce modifier order

Issue: -

## Description

Checks that the order of modifiers conforms to the suggestions in the [Java Language specification, sections 8.1.1, 8.3.1, 8.4.3](http://docs.oracle.com/javase/specs/jls/se8/html/jls-8.html) and [9.4](https://docs.oracle.com/javase/specs/jls/se8/html/jls-9.html). The correct order is: 

  1. `public`
  2. `protected`
  3. `private`
  4. `abstract`
  5. `default`
  6. `static`
  7. `final`
  8. `transient`
  9. `volatile`
  10. `synchronized`
  11. `native`
  12. `strictfp`

ATTENTION: We skip [type annotations](http://www.oracle.com/technetwork/articles/java/ma14-architect-annotations-2177655.html) from validation. 

## Examples

To configure the check: 
    
    
    <module name="ModifierOrder"/>

## Further Reading

* [checkstyle - ModifierOrder](http://checkstyle.sourceforge.net/config_modifier.html#ModifierOrder)
