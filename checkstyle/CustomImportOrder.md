Pattern: Wrong custom import order or grouping

Issue: -

## Description

Checks that the groups of import declarations appear in the order specified by the user. If there is an import but its group is not specified in the configuration such an import should be placed at the end of the import list. 

## Examples

To configure the check so that it matches default Eclipse formatter configuration (tested on Kepler and Luna releases):

  - group of static imports is on the top
  - groups of non-static imports: "java" and "javax" packages first, then "org" and then all other imports
  - imports will be sorted in the groups
  - groups are separated by, at least, one blank line

Notes:

  - "com" package is not mentioned on configuration, because it is ignored by Eclipse Kepler and Luna (looks like Eclipse defect)
  - configuration below doesn't work in all 100% cases due to inconsistent behavior prior to Mars release, but covers most scenarios


```xml
<module name="CustomImportOrder">
    <property name="customImportOrderRules" value="STATIC###STANDARD_JAVA_PACKAGE###SPECIAL_IMPORTS"/>
    <property name="specialImportsRegExp" value="^org\."/>
    <property name="sortImportsInGroupAlphabetically" value="true"/>
    <property name="separateLineBetweenGroups" value="true"/>
</module>
```
        

To configure the check so that it matches default Eclipse formatter configuration (tested on Mars release):

  - group of static imports is on the top
  - groups of non-static imports: "java" and "javax" packages first, then "org" and "com", then all other imports as one group
  - imports will be sorted in the groups
  - groups are separated by, at least, one blank line


```xml
<module name="CustomImportOrder">
    <property name="customImportOrderRules" value="STATIC###STANDARD_JAVA_PACKAGE###SPECIAL_IMPORTS###THIRD_PARTY_PACKAGE"/>
    <property name="specialImportsRegExp" value="^org\."/>
    <property name="thirdPartyPackageRegExp" value="^com\."/>
    <property name="sortImportsInGroupAlphabetically" value="true"/>
    <property name="separateLineBetweenGroups" value="true"/>
</module>
```
        

To configure the check so that it matches default IntelliJ IDEA formatter configuration (tested on v14):

  - group of static imports is on the bottom
  - groups of non-static imports: all imports except of "javax" and "java", then "javax" and "java"
  - imports will be sorted in the groups
  - groups are separated by, at least, one blank line

Note: "separated" option is disabled because IDEA default has blank line between "java" and static imports, and no blank line between "javax" and "java"


```xml
<module name="CustomImportOrder">
    <property name="customImportOrderRules" value="THIRD_PARTY_PACKAGE###SPECIAL_IMPORTS###STANDARD_JAVA_PACKAGE###STATIC"/>
    <property name="specialImportsRegExp" value="^javax\."/>
    <property name="standardPackageRegExp" value="^java\."/>
    <property name="sortImportsInGroupAlphabetically" value="true"/>
    <property name="separateLineBetweenGroups" value="false"/>
</module>
```
        

To configure the check so that it matches default NetBeans formatter configuration (tested on v8):

  - groups of non-static imports are not defined, all imports will be sorted as a one group
  - static imports are not separated, they will be sorted along with other imports


```xml
<module name="CustomImportOrder"/>
```
        

To set RegExps for THIRD_PARTY_PACKAGE and STANDARD_JAVA_PACKAGE groups use thirdPartyPackageRegExp and standardPackageRegExp options. 


```xml
<module name="CustomImportOrder">
    <property name="customImportOrderRules" value="STATIC###SAME_PACKAGE(3)###THIRD_PARTY_PACKAGE###STANDARD_JAVA_PACKAGE"/>
    <property name="thirdPartyPackageRegExp" value="^(com|org)\."/>
    <property name="standardPackageRegExp" value="^(java|javax)\."/>
</module>
```
        

Also, this check can be configured to force empty line separator between import groups. For example. 


```xml
<module name="CustomImportOrder">
    <property name="separateLineBetweenGroups" value="true"/>
</module>
```
        

It is possible to enforce [ ASCII sort order](https://en.wikipedia.org/wiki/ASCII#Order) of imports in groups using the following configuration: 


```xml
<module name="CustomImportOrder">
    <property name="sortImportsInGroupAlphabetically" value="true"/>
</module>
```
       

Example of ASCII order: 


```java
import java.awt.Dialog;
import java.awt.Window;
import java.awt.color.ColorSpace;
import java.awt.Frame; // violation here - in ASCII order 'F' should go before 'c',
          // as all uppercase come before lowercase letters
```
       

To force checking imports sequence such as: 


```java
package com.puppycrawl.tools.checkstyle.imports;

import com.google.common.annotations.GwtCompatible;
import com.google.common.annotations.Beta;
import com.google.common.annotations.VisibleForTesting;

import org.abego.treelayout.Configuration;

import static sun.tools.util.ModifierFilter.ALL_ACCESS;

import com.google.common.annotations.GwtCompatible; // violation here - should be in the
                                                    // THIRD_PARTY_PACKAGE group
import android.*;
```
 
 
configure as follows: 


```xml
<module name="CustomImportOrder">
    <property name="customImportOrderRules" value="SAME_PACKAGE(3)###THIRD_PARTY_PACKAGE###STATIC###SPECIAL_IMPORTS"/>
    <property name="specialImportsRegExp" value="^android\."/>
</module>
```

## Further Reading

* [checkstyle - CustomImportOrder](https://checkstyle.sourceforge.io/checks/imports/customimportorder.html#CustomImportOrder)
