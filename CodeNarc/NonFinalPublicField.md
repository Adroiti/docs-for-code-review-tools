Pattern: Non-`final` public field

Issue: -

## Description

Finds code that violates secure coding principles for mobile code by declaring a member variable `public` but not `final`.

All public member variables in an Applet and in classes used by an Applet should be declared final to prevent an attacker from manipulating or gaining unauthorized access to the internal state of the Applet.

## Further Reading

* [CodeNarc - NonFinalPublicField](https://codenarc.github.io/CodeNarc/codenarc-rules-security.html#nonfinalpublicfield-rule)