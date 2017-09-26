Pattern: Setting locale across the entire JVM

Issue: -

## Description

Checks for calls to `Locale.setDefault()`, or `Locale.default = Xxx`, which sets the Locale across the entire JVM. That can impact other applications on the same web server, for instance.

Since changing the default locale may affect many different areas of functionality, this method should only be used if the caller is prepared to reinitialize locale-sensitive code running within the same Java Virtual Machine.

Example of violations:

``` groovy
Locale.setDefault(Locale.UK)                                // violation
java.util.Locale.setDefault(Locale.FRANCE)                  // violation
Locale.setDefault(Locale.Category.DISPLAY, Locale.JAPAN)    // violation

Locale.default = Locale.UK                                  // violation
```

## Further Reading

* [CodeNarc - LocaleSetDefault](http://codenarc.sourceforge.net/codenarc-rules-design.html#LocaleSetDefault)