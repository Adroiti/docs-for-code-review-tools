Pattern: Possible issue in file name and/or folder path

Issue: -

## Description

Implementation of a check that looks for a file name and/or path match (or mis-match) against specified patterns. It can also be used to verify files match specific naming patterns not covered by other checks (Ex: properties, xml, etc.). 

When customizing the check, the properties are applied in a specific order. The fileExtensions property first picks only files that match any of the specific extensions supplied. Once files are matched against the fileExtensions, the match property is then used in conjunction with the patterns to determine if the check is looking for a match or mis-match on those files. If the fileNamePattern is supplied, the matching is only applied to the fileNamePattern and not the folderPattern. If no fileNamePattern is supplied, then matching is applied to the folderPattern only and will result in all files in a folder to be reported on violations. If no folderPattern is supplied, then all folders that checkstyle finds are examined for violations. The ignoreFileNameExtensions property drops the file extension and applies the fileNamePattern only to the rest of file name. For example, if the file is named 'test.java' and this property is turned on, the pattern is only applied to 'test'. 

If this check is configured with no properties, then the default behavior of this check is to report file names with spaces in them. When at least one pattern property is supplied, the entire check is under the user's control to allow them to fully customize the behavior. 

It is recommended that if you create your own pattern, to also specify a custom error message. This allows the error message printed to be clear what the violation is, especially if multiple RegexpOnFilename checks are used. Argument 0 for the message populates the check's folderPattern. Argument 1 for the message populates the check's fileNamePattern. The file name is not passed as an argument since it is part of CheckStyle's default error messages. 

## Examples

To configure the check to report file names that contain a space: 
    
    
    <module name="RegexpOnFilename"/>
            

To configure the check to force picture files to not be 'gif': 
    
    
    <module name="RegexpOnFilename">
      <property name="fileNamePattern" value="\.gif$"/>
    </module>
            

OR: 
    
    
    <module name="RegexpOnFilename">
      <property name="fileNamePattern" value="."/>
      <property name="fileExtensions" value="gif"/>
    </module>
            

To configure the check to only allow property and xml files to be located in the resource folder: 
    
    
    <module name="RegexpOnFilename">
      <property name="folderPattern" value="[\\/]src[\\/]\w+[\\/]resources[\\/]"/>
      <property name="match" value="false"/>
      <property name="fileExtensions" value="properties, xml"/>
    </module>
            

To configure the check to only allow Java and XML files in your folders use the below. 
    
    
    <module name="RegexpOnFilename">
      <property name="fileNamePattern" value="\.(java|xml)$"/>
      <property name="match" value="false"/>
    </module>
            

To configure the check to only allow Java and XML files only in your source folder and ignore any other folders:  
**Note:** 'folderPattern' must be specified if checkstyle is analyzing more than the normal source folder, like the 'bin' folder where class files can be located. 
    
    
    <module name="RegexpOnFilename">
      <property name="folderPattern" value="[\\/]src[\\/]"/>
      <property name="fileNamePattern" value="\.(java|xml)$"/>
      <property name="match" value="false"/>
    </module>
            

To configure the check to only allow file names to be camel case: 
    
    
    <module name="RegexpOnFilename">
      <property name="fileNamePattern" value="^([A-Z][a-z0-9]+\.?)+$"/>
      <property name="match" value="false"/>
      <property name="ignoreFileNameExtensions" value="true"/>
    </module>

## Further Reading

* [checkstyle - RegexpOnFilename](http://checkstyle.sourceforge.net/config_regexp.html#RegexpOnFilename)