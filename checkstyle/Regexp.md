Pattern: Possible issue by regular expression

Issue: -

## Description

A check that makes sure that a specified pattern exists, exists less than a set number of times, or does not exist in the file. 

It differs from them in that it works in multi-line mode. Its regular expression can span multiple lines and it checks this against the whole file at once. The others work in single-line mode. Their single or multiple regular expressions can only span one line. They check each of these against each line in the file in turn. 

**Note:** Because of the different mode of operation there may be some changes in the regular expressions used to achieve a particular end. 

In multi-line mode...

  - `^` means the beginning of a line, as opposed to beginning of the input.
  - For beginning of the input use `\A`.
  - `$` means the end of a line, as opposed to the end of the input.
  - For end of input use `\Z`.
  - Each line in the file is terminated with a line feed character.

**Note:** Not all regular expression engines are created equal. Some provide extra functions that others do not and some elements of the syntax may vary. This check makes use of the [java.util.regex package](https://docs.oracle.com/javase/7/docs/api/java/util/regex/package-summary.html); please check its documentation for details of how to construct a regular expression to achieve a particular goal. 

**Note:** When entering a regular expression as a parameter in the XML config file you must also take into account the XML rules. e.g. if you want to match a < symbol you need to enter &lt;. The regular expression should be entered on one line. 

## Examples

The following examples are mainly copied from the other 3 checks mentioned above, to show how the same results can be achieved using this check in place of them. 

**To use like Required Regexp check:**

An example of how to configure the check to make sure a copyright statement is included in the file: 

The statement. 


```java
 // This code is copyrighted
```
        

The check. 


```java
 <module name="Regexp">
 <property name="format" value="// This code is copyrighted"/>
 </module>
```
        

Your statement may be multi-line. 


```java
 // This code is copyrighted
 // (c) MyCompany
```
        

Then the check would be. 


```java
 <module name="Regexp">
 <property name="format" value="// This code is copyrighted\n// \(c\) MyCompany"/>
 </module>
```
        

**Note:** To search for parentheses () in a regular expression you must escape them like \\(\\). This is required by the Regexp engine, otherwise it will think they are special instruction characters. 

And to make sure it appears only once: 


```java
 <module name="Regexp">
 <property name="format" value="// This code is copyrighted\n// \(c\) MyCompany"/>
 <property name="duplicateLimit" value="0"/>
 </module>
```
        

It can also be useful to attach a meaningful message to the check: 


```java
 <module name="Regexp">
 <property name="format" value="// This code is copyrighted\n// \(c\) MyCompany"/>
 <property name="message" value="Copyright"/>
 </module>
```
        

**To use like illegal Regexp check:**

An example of how to configure the check to make sure there are no calls to `System.out.println`: 


```java
 <module name="Regexp">
 <!-- . matches any character, so we need to escape it and use \. to match dots. -->
 <property name="format" value="System\.out\.println"/>
 <property name="illegalPattern" value="true"/>
 </module>
```
        

You may want to make the above check ignore comments, like this: 


```java
 <module name="Regexp">
 <property name="format" value="System\.out\.println"/>
 <property name="illegalPattern" value="true"/>
 <property name="ignoreComments" value="true"/>
 </module>
```
        

An example of how to configure the check to find trailing whitespace at the end of a line: 


```java
 <module name="Regexp">
 <property name="format" value="[ \t]+$"/>
 <property name="illegalPattern" value="true"/>
 <property name="message" value="Trailing whitespace"/>
 </module>
```
        

An example of how to configure the check to find case-insensitive occurrences of "debug": 


```java
 <module name="Regexp">
 <property name="format" value="(?i)debug"/>
 <property name="illegalPattern" value="true"/>
 </module>
```
        

**Note:** The (?i) at the beginning of the regular expression tells the Regexp engine to ignore the case. 

There is also a feature to limit the number of errors reported. When the limit is reached the check aborts with a message reporting that the limit has been reached. The default limit setting is 100, but this can be change as shown in the following example. 


```java
 <module name="Regexp">
 <property name="format" value="(?i)debug"/>
 <property name="illegalPattern" value="true"/>
 <property name="errorLimit" value="1000"/>
 </module>
```
        

**To use like [RegexpHeader ](http://checkstyle.sourceforge.net/config_header.html#RegexpHeader):**

To configure the check to verify that each file starts with the following multi-line header. 

Note the following:

  - \A means the start of the file.
  - The date can be any 4 digit number.


```java
 // Copyright (C) 2004 MyCompany
 // All rights reserved
```
        


```java
 <module name="Regexp">
 <property
 name="format"
 value="\A// Copyright \(C\) \d\d\d\d MyCompany\n// All rights reserved"/>
 </module>
```
        

A more complex example. Note how the import and Javadoc multi-lines are handled, there can be any number of them. 


```java
 ///////////////////////////////////////////////////////////////////////
 // checkstyle:
 // Checks Java source code for adherence to a set of rules.
 // Copyright (C) 2004  Oliver Burn
 // Last modification by $Author A.N.Other$
 ///////////////////////////////////////////////////////////////////////
 
 package com.puppycrawl.checkstyle;
 
 import java.util.thing1;
 import java.util.thing2;
 import java.util.thing3;
 
 /**
 * Javadoc line 1
 * Javadoc line 2
 * Javadoc line 3
 */
 
 <module name="Regexp">
 <property  name="format"
 value="\A/{71}\n// checkstyle:\n// Checks Java source code for
 adherence to a set of rules\.\n// Copyright \(C\) \d\d\d\d  Oliver Burn\n
 // Last modification by \$Author.*\$\n/{71}\n\npackage [\w\.]*;\n\n
 (import [\w\.]*;\n)*\n/\*\*\n( \*[^/]*\n)* \*/"/>
 </module>
```

**Note:** To search for things that mean something in XML, like < you need to escape them like &lt;. This is required so the XML parser does not act on them, but instead passes the correct character to the regexp engine.

## Further Reading

* [checkstyle - Regexp](https://checkstyle.sourceforge.io/checks/regexp/regexp.html#Regexp)
