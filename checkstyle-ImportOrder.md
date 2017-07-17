Pattern: Wrong import order or grouping

Issue: -

## Description

Checks the ordering/grouping of imports. Features are:

  - groups imports: ensures that groups of imports come in a specific order (e.g., `java.` comes first, `javax.` comes second, then everything else)
  - adds a separation between groups : ensures that a blank line sit between each group
  - import groups aren't separated internally: ensures that each group aren't separated internally by blank line or comment
  - sorts imports inside each group: ensures that imports within each group are in lexicographic order
  - sorts according to case: ensures that the comparison between imports is case sensitive, in [ASCII sort order](https://en.wikipedia.org/wiki/ASCII#Order)
  - groups static imports: ensures the relative order between regular imports and static imports (see [import orders](http://checkstyle.sourceforge.net/property_types.html#importOrder))

Examples section contains examples that work with default formatter configurations of Eclipse, IntelliJ IDEA and NetBeans 

## Examples

To configure the check so that it matches default Eclipse formatter configuration (tested on Kepler and Luna releases):

  - group of static imports is on the top
  - groups of non-static imports: "java" and "javax" packages first, then "org" and then all other imports
  - imports will be sorted in the groups
  - groups are separated by, at least, one blank line and aren't separated internally

Notes:

  - "com" package is not mentioned on configuration, because it is ignored by Eclipse Kepler and Luna (looks like Eclipse defect)
  - configuration below doesn't work in all 100% cases due to inconsistent behavior prior to Mars release, but covers most scenarios
    
    
    <module name="ImportOrder">
        <property name="groups" value="/^java\./,javax,org"/>
        <property name="ordered" value="true"/>
        <property name="separated" value="true"/>
        <property name="option" value="above"/>
        <property name="sortStaticImportsAlphabetically" value="true"/>
    </module>
            

To configure the check so that it matches default Eclipse formatter configuration (tested on Mars release):

  - group of static imports is on the top
  - groups of non-static imports: "java" and "javax" packages first, then "org" and "com", then all other imports as one group
  - imports will be sorted in the groups
  - groups are separated by, at least, one blank line and aren't separated internally
    
    
    <module name="ImportOrder">
        <property name="groups" value="/^java\./,javax,org,com"/>
        <property name="ordered" value="true"/>
        <property name="separated" value="true"/>
        <property name="option" value="above"/>
        <property name="sortStaticImportsAlphabetically" value="true"/>
    </module>
            

To configure the check so that it matches default IntelliJ IDEA formatter configuration (tested on v14):

  - group of static imports is on the bottom
  - groups of non-static imports: all imports except of "javax" and "java", then "javax" and "java"
  - imports will be sorted in the groups
  - groups are separated by, at least, one blank line and aren't separated internally

Note: "separated" option is disabled because IDEA default has blank line between "java" and static imports, and no blank line between "javax" and "java"
    
    
    <module name="ImportOrder">
        <property name="groups" value="*,javax,java"/>
        <property name="ordered" value="true"/>
        <property name="separated" value="false"/>
        <property name="option" value="bottom"/>
        <property name="sortStaticImportsAlphabetically" value="true"/>
    </module>
            

To configure the check so that it matches default NetBeans formatter configuration (tested on v8):

  - groups of non-static imports are not defined, all imports will be sorted as a one group
  - static imports are not separated, they will be sorted along with other imports
    
    
    <module name="ImportOrder">
        <property name="option" value="inflow"/>
    </module>
            

To configure the check allows static imports grouped to the **top** being sorted alphabetically: 
    
    
    <module name="ImportOrder">
        <property name="sortStaticImportsAlphabetically" value="true"/>
        <property name="option" value="top"/>
    </module>
            
    
    
    import static java.lang.Math.PI;
    import static java.lang.Math.abs; // OK, alphabetical case sensitive ASCII order, 'P' < 'a'
    import static org.abego.treelayout.Configuration.AlignmentInLevel; // OK, alphabetical order
    
    import org.abego.*;
    
    import java.util.Set; //  Wrong order for 'java.util.Set' import.
    
    public class SomeClass { ... }
            

The following example shows the idea of 'useContainerOrderingForStatic' option that is useful for Eclipse IDE users to match ordering validation. This is how the import comparison works for static imports: we first compare the container of the static import, container is the type enclosing the static element being imported. When the result of the comparison is 0 (containers are equal), we compare the fully qualified import names. For e.g. this is what is considered to be container names for the given example: import static HttpConstants.COLON => HttpConstants import static HttpHeaders.addHeader => HttpHeaders import static HttpHeaders.setHeader => HttpHeaders import static HttpHeaders.Names.DATE => HttpHeaders.Names According to this logic, HttpHeaders.Names should come after HttpHeaders. 
    
    
    <module name="ImportOrder">
        <property name="useContainerOrderingForStatic" value="true"/>
        <property name="ordered" value="true"/>
        <property name="option" value="top"/>
        <property name="caseSensitive" value="false"/>
        <property name="sortStaticImportsAlphabetically" value="true"/>
    </module>
            
    
    
    import static io.netty.handler.codec.http.HttpConstants.COLON;
    import static io.netty.handler.codec.http.HttpHeaders.addHeader;
    import static io.netty.handler.codec.http.HttpHeaders.setHeader;
    import static io.netty.handler.codec.http.HttpHeaders.Names.DATE;
    
    public class InputEclipseStaticImportsOrder { }
            
    
    
    <module name="ImportOrder">
        <property name="useContainerOrderingForStatic" value="false"/>
        <property name="ordered" value="true"/>
        <property name="option" value="top"/>
        <property name="caseSensitive" value="false"/>
        <property name="sortStaticImportsAlphabetically" value="true"/>
    </module>
            
    
    
    import static io.netty.handler.codec.http.HttpConstants.COLON;
    import static io.netty.handler.codec.http.HttpHeaders.addHeader;
    import static io.netty.handler.codec.http.HttpHeaders.setHeader;
    import static io.netty.handler.codec.http.HttpHeaders.Names.DATE; // violation
    
    public class InputEclipseStaticImportsOrder { }

## Further Reading

* [checkstyle - ImportOrder](http://checkstyle.sourceforge.net/config_imports.html#ImportOrder)