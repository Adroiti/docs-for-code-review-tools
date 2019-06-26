Pattern: Missing nonce verification

Issue: -

## Description

Checks that nonce verification accompanies form processing.

If your plugin allows users to submit data; be it on the Admin or the Public side; you have to make sure that the user is who they say they are and that they have the necessary capability to perform the action. Doing both in tandem means that data is only changing when the user _expects_ it to be changing.

## Further Reading

* [Nonces on Plugin Developer Handbook](https://developer.wordpress.org/plugins/security/nonces)
* [WordPress.Security.NonceVerification](https://github.com/WordPress/WordPress-Coding-Standards/tree/develop/WordPress/Sniffs/Security/NonceVerificationSniff.php)