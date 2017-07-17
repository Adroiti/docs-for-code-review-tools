Pattern: Incorrect translation of code

Issue: -

## Description

A [FileSetCheck](http://checkstyle.sourceforge.net/config.html#Overview) that ensures the correct translation of code by checking property files for consistency regarding their keys. Two property files describing one and the same context are consistent if they contain the same keys. TranslationCheck also can check an existence of required translations which must exist in project, if `requiredTranslations` option is used. 

Consider the following properties file in the same directory: 
    
    
    #messages.properties
    hello=Hello
    cancel=Cancel
    
    #messages_de.properties
    hell=Hallo
    ok=OK
            

The Translation check will find the typo in the German `hello` key, the missing `ok` key in the default resource file and the missing `cancel` key in the German resource file: 
    
    
    messages_de.properties: Key 'hello' missing.
    messages_de.properties: Key 'cancel' missing.
    messages.properties: Key 'hell' missing.
    messages.properties: Key 'ok' missing.
            

Attention: this check could produce false-positives if it is used with [Checker](http://checkstyle.sourceforge.net/config.html#Checker) that use cache (property "cacheFile") This is known design problem, will be addressed at [issue](https://github.com/checkstyle/checkstyle/issues/3539). 

## Examples

To configure the check to check only files which have '.properties' and '.translations' extensions: 
    
    
    <module name="Translation">
        <property name="fileExtensions" value="properties, translations"/>
    </module>
            

Note, that files with the same path and base name but which have different extensions will be considered as files that belong to different resource bundles. 

An example of how to configure the check to validate only bundles which base names start with "ButtonLabels": 
    
    
    <module name="Translation">
        <property name="baseName" value="^ButtonLabels.*$"/>
    </module>
            

To configure the check to check existence of Japanese and French translations: 
    
    
    <module name="Translation">
        <property name="requiredTranslations" value="ja, fr"/>
    </module>
            

The following example shows how the check works if there is a message bundle which element name contains language code, county code, platform name. Consider that we have the below configuration: 
    
    
    <module name="Translation">
        <property name="requiredTranslations" value="es, fr, de"/>
    </module>
            

As we can see from the configuration, the TranslationCheck was configured to check an existence of 'es', 'fr' and 'de' translations. Lets assume that we have the resource bundle: 
    
    
    messages_home.properties
    messages_home_es_US.properties
    messages_home_fr_CA_UNIX.properties
            

Than the check will rise the following violation: "0: Properties file 'messages_home_de.properties' is missing."

## Further Reading

* [checkstyle - Translation](http://checkstyle.sourceforge.net/config_misc.html#Translation)