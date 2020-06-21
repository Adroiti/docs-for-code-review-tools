Pattern: Use of `File.createTempFile()`

Issue: -

## Description

The `File.createTempFile()` method is insecure, and has been deprecated by the ESAPI secure coding library. It has been replaced by the ESAPI `Randomizer.getRandomFilename(String)` method.

## Further Reading

* [ESAPI API - Interface Randomizer](https://static.javadoc.io/org.owasp.esapi/esapi/2.1.0.1/org/owasp/esapi/Randomizer.html)
* [OWASP - ESAPI Secure Coding Guideline](https://www.owasp.org/index.php/ESAPI_Secure_Coding_Guideline#Banned_APIs)
* [CodeNarc - FileCreateTempFile](https://codenarc.github.io/CodeNarc/codenarc-rules-security.html#filecreatetempfile-rule)