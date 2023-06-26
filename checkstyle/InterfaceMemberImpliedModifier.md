Pattern: Implicit modifier on interface member

Issue: -

## Description

Methods in interfaces are `public` by default, however from _Java 9_ they can also be `private`. This check provides the ability to enforce that `public` is explicitly coded and not implicitly added by the compiler. 

From _Java 8_, there are three types of methods in interfaces - static methods marked with `static`, default methods marked with `default` and abstract methods which do not have to be marked with anything. From _Java 9_, there are also private methods marked with `private`. This check provides the ability to enforce that `abstract` is explicitly coded and not implicitly added by the compiler. 

Fields in interfaces are always `public static final` and as such the compiler does not require these modifiers. This check provides the ability to enforce that these modifiers are explicitly coded and not implicitly added by the compiler. 

Nested types within an interface are always `public static` and as such the compiler does not require the `public static` modifiers. This check provides the ability to enforce that the `public` and `static` modifiers are explicitly coded and not implicitly added by the compiler. 
    
```java 
public interface AddressFactory {
  // check enforces code contains "public static final"
  public static final String UNKNOWN = "Unknown";

  String OTHER = "Other";  // violation

  // check enforces code contains "public" or "private"
  public static AddressFactory instance();

  // check enforces code contains "public abstract"
  public abstract Address createAddress(String addressLine, String city);

  List<Address> findAddresses(String city);  // violation

  // check enforces default methods are explicitly declared "public"
  public default Address createAddress(String city) {
	return createAddress(UNKNOWN, city);
  }

  default Address createOtherAddress() {  // violation
	return createAddress(OTHER, OTHER);
  }
}
```
           
Rationale: Methods, fields and nested types are treated differently depending on whether they are part of an interface or part of a class. For example, by default methods are package-scoped on classes, but public in interfaces. However, from _Java 8_ onwards, interfaces have changed to be much more like abstract classes. Interfaces now have static and instance methods with code. Developers should not have to remember which modifiers are required and which are implied. This check allows the simpler alternative approach to be adopted where the implied modifiers must always be coded explicitly. 

## Examples

This example checks that all implicit modifiers on methods, fields and nested types are explicitly specified in interfaces. 

Configuration: 
    
```xml
<module name="InterfaceMemberImpliedModifier"/>
```      

Code: 
    
   
```java   
public interface AddressFactory {

  public static final String UNKNOWN = "Unknown";  // valid

  String OTHER = "Other";  // violation

  public static AddressFactory instance();  // valid

  public abstract Address createAddress(String addressLine, String city);  // valid

  List<Address> findAddresses(String city);  // violation

  interface Address {  // violation

	String getCity();  // violation
  }
}
```
            

This example checks that all implicit modifiers on methods and fields are explicitly specified, but nested types do not need to be. 

Configuration: 
    
```xml
<module name="InterfaceMemberImpliedModifier">
  <property name="violateImpliedPublicNested" value="false"/>
  <property name="violateImpliedStaticNested" value="false"/>
</module>
```

Code: 

```java
    public interface RoadFeature {
    
      String STOP = "Stop";  // violation
    
      enum Lights {  // valid because of configured properties
    
        RED, YELLOW, GREEN;
      }
    }
```	

## Further Reading

* [checkstyle - InterfaceMemberImpliedModifier](https://checkstyle.sourceforge.io/checks/modifier/interfacememberimpliedmodifier.html#InterfaceMemberImpliedModifier)