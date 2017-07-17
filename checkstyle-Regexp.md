Pattern: Possible issue by regular expression

Issue: -

## Description

A check that makes sure that a specified pattern exists, exists less than a set number of times, or does not exist in the file. 

This check combines all the functionality provided by [RegexpHeader](http://checkstyle.sourceforge.net/config_header.html#RegexpHeader) except supplying the regular expression from a file. 

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
    
    
              // This code is copyrighted
            

The check. 
    
    
              <module name="Regexp">
              <property name="format" value="// This code is copyrighted"/>
              </module>
            

Your statement may be multi-line. 
    
    
              // This code is copyrighted
              // (c) MyCompany
            

Then the check would be. 
    
    
              <module name="Regexp">
              <property name="format" value="// This code is copyrighted\n// \(c\) MyCompany"/>
              </module>
            

**Note:** To search for parentheses () in a regular expression you must escape them like \\(\\). This is required by the Regexp engine, otherwise it will think they are special instruction characters. 

And to make sure it appears only once: 
    
    
              <module name="Regexp">
              <property name="format" value="// This code is copyrighted\n// \(c\) MyCompany"/>
              <property name="duplicateLimit" value="0"/>
              </module>
            

It can also be useful to attach a meaningful message to the check: 
    
    
              <module name="Regexp">
              <property name="format" value="// This code is copyrighted\n// \(c\) MyCompany"/>
              <property name="message" value="Copyright"/>
              </module>
            

**To use like illegal Regexp check:**

An example of how to configure the check to make sure there are no calls to `System.out.println`: 
    
    
              <module name="Regexp">
              <!-- . matches any character, so we need to escape it and use \. to match dots. -->
              <property name="format" value="System\.out\.println"/>
              <property name="illegalPattern" value="true"/>
              </module>
            

You may want to make the above check ignore comments, like this: 
    
    
              <module name="Regexp">
              <property name="format" value="System\.out\.println"/>
              <property name="illegalPattern" value="true"/>
              <property name="ignoreComments" value="true"/>
              </module>
            

An example of how to configure the check to find trailing whitespace at the end of a line: 
    
    
              <module name="Regexp">
              <property name="format" value="[ \t]+$"/>
              <property name="illegalPattern" value="true"/>
              <property name="message" value="Trailing whitespace"/>
              </module>
            

An example of how to configure the check to find case-insensitive occurrences of "debug": 
    
    
              <module name="Regexp">
              <property name="format" value="(?i)debug"/>
              <property name="illegalPattern" value="true"/>
              </module>
            

**Note:** The (?i) at the beginning of the regular expression tells the Regexp engine to ignore the case. 

There is also a feature to limit the number of errors reported. When the limit is reached the check aborts with a message reporting that the limit has been reached. The default limit setting is 100, but this can be change as shown in the following example. 
    
    
              <module name="Regexp">
              <property name="format" value="(?i)debug"/>
              <property name="illegalPattern" value="true"/>
              <property name="errorLimit" value="1000"/>
              </module>
            

**To use like [RegexpHeader ](http://checkstyle.sourceforge.net/config_header.html#RegexpHeader):**

To configure the check to verify that each file starts with the following multi-line header. 

Note the following:

  - \A means the start of the file.
  - The date can be any 4 digit number.
    
    
              // Copyright (C) 2004 MyCompany
              // All rights reserved
            
    
    
              <module name="Regexp">
              <property
              name="format"
              value="\A// Copyright \(C\) \d\d\d\d MyCompany\n// All rights reserved"/>
              </module>
            

A more complex example. Note how the import and Javadoc multi-lines are handled, there can be any number of them. 
    
    
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
              <property
              name="format"
              value="\A/{71}\n// checkstyle:\n// Checks Java source code for
              adherence to a set of rules\.\n// Copyright \(C\) \d\d\d\d  Oliver Burn\n
              // Last modification by \$Author.*\$\n/{71}\n\npackage [\w\.]*;\n\n
              (import [\w\.]*;\n)*\n/\*\*\n( \*[^/]*\n)* \*/"/>
              </module>
            

**More examples:**

The next 2 examples deal with the following example Java source file: 
    
    
              /*
              * PID.java
              *
              * Copyright (c) 2001 ACME
              * 123 Some St.
              * Somewhere.
              *
              * This software is the confidential and proprietary information of ACME.
              * ("Confidential Information"). You shall not disclose such
              * Confidential Information and shall use it only in accordance with
              * the terms of the license agreement you entered into with ACME.
              *
              * $Log: config_misc.xml,v $
              * Revision 1.7  2007/01/16 12:16:35  oburn
              * Removing all reference to mailing lists
              *
              * Revision 1.6  2005/12/25 16:13:10  o_sukhodolsky
              * Fix for rfe 1248106 (TYPECAST is now accepted by NoWhitespaceAfter)
              *
              * Fix for rfe 953266 (thanks to Paul Guyot (pguyot) for submitting patch)
              * IllegalType can be configured to accept some abstract classes which
              * matches to regexp of illegal type names (property legalAbstractClassNames)
              *
              * TrailingComment now can be configured to accept some trailing comments
              * (such as NOI18N) (property legalComment, rfe 1385344).
              *
              * Revision 1.5  2005/11/06 11:54:12  oburn
              * Incorporate excellent patch [1344344] Consolidation of regexp checks.
              *
              * Revision 1.3.8.1  2005/10/11 14:26:32  someone
              * Fix for bug 251.  The broken bit is fixed
              */
    
              package com.acme.tools;
    
              import com.acme.thing1;
              import com.acme.thing2;
              import com.acme.thing3;
    
              /**
              *
              * <P>
              *   <I>This software is the confidential and proprietary information of
              *   ACME (<B>"Confidential Information"</B>). You shall not
              *   disclose such Confidential Information and shall use it only in
              *   accordance with the terms of the license agreement you entered into
              *   with ACME.</I>
              * </P>
              *
              * &#169; copyright 2002 ACME
              *
              * @author   Some Body
              */
              public class PID extends StateMachine implements WebObject.Constants {
    
              /** Javadoc. */
              public static final int A_SETPOINT = 1;
              .
              .
              .
              } // class PID
            

This checks for the presence of the header, the first 16 lines. 

Note the following:

  - Line 2 and 13 contain the file name. These are checked to make sure they are the same, and that they match the class name.
  - The date can be any 4 digit number.
    
    
              <module name="Regexp">
              <property
              name="format"
              value="\A/\*\n \* (\w*)\.java\n \*\n \* Copyright \(c\)
              \d\d\d\d ACME\n \* 123 Some St\.\n \* Somewhere\.\n \*\n
              \* This software is the confidential and proprietary information
              of ACME\.\n \* \(&quot;Confidential Information&quot;\)\. You
              shall not disclose such\n \* Confidential Information and shall
              use it only in accordance with\n \* the terms of the license
              agreement you entered into with ACME\.\n \*\n
              \* \$Log: config_misc\.xml,v $
              \* Revision 1\.7  2007/01/16 12:16:35  oburn
              \* Removing all reference to mailing lists
              \* \
              \* Revision 1.6  2005/12/25 16:13:10  o_sukhodolsky
              \* Fix for rfe 1248106 \(TYPECAST is now accepted by NoWhitespaceAfter\)
              \* \
              \* Fix for rfe 953266 \(thanks to Paul Guyot \(pguyot\) for submitting patch\)
              \* IllegalType can be configured to accept some abstract classes which
              \* matches to regexp of illegal type names \(property legalAbstractClassNames\)
              \*
              \* TrailingComment now can be configured to accept some trailing comments
              \* \(such as NOI18N\) \(property legalComment, rfe 1385344\).
              \*
              \* Revision 1.5  2005/11/06 11:54:12  oburn
              \* Incorporate excellent patch \[ 1344344 \] Consolidation of regexp checks.
              \* \\n(.*\n)*([\w|\s]*( class | interface )\1)"/>
              <property name="message" value="Correct header not found"/>
              </module>
            

This checks for the presence of a copyright notice within the class Javadoc, lines 24 to 37. 
    
    
              <module name="Regexp">
              <property
              name="format"
              value="(/\*\*\n)( \*.*\n)*( \* &lt;P&gt;\n \*   &lt;I&gt;
              This software is the confidential and proprietary information of\n
              \*   ACME \(&lt;B&gt;&quot;Confidential Information&quot;&lt;/B&gt;
              \)\. You shall not\n \*   disclose such Confidential Information
              and shall use it only in\n \*   accordance with the terms of the
              license agreement you entered into\n \*   with ACME\.&lt;/I&gt;\n
              \* &lt;/P&gt;\n \*\n \* &#169; copyright \d\d\d\d ACME\n
              \*\n \* @author .*)(\n\s\*.*)*/\n[\w|\s]*( class | interface )"/>
              <property name="message" value="Copyright in class/interface Javadoc"/>
              <property name="duplicateLimit" value="0"/>
              </module>
            

**Note:** To search for things that mean something in XML, like < you need to escape them like &lt;. This is required so the XML parser does not act on them, but instead passes the correct character to the regexp engine.

## Further Reading

* [checkstyle - Regexp](http://checkstyle.sourceforge.net/config_regexp.html#Regexp)