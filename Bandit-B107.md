Pattern: Use of hard-coded password argument defaults

Issue: -

## Description

The use of hard-coded passwords increases the possibility of password guessing
tremendously. This rule looks for all function definitions that specify
a default string literal for some argument. It checks that the argument does
not look like a password.

Variables are considered to look like a password if they have match any one
of:

  - "password"
  - "pass"
  - "passwd"
  - "pwd"
  - "secret"
  - "token"
  - "secrete"

Note: this can be noisy and may generate false positives.

**Config Options:**

None

Example of **incorrect** code:

```python

>> Issue: [B107:hardcoded_password_default] Possible hardcoded
password: 'Admin'
   Severity: Low   Confidence: Medium
   Location: ./examples/hardcoded-passwords.py:1

1def someFunction(user, password="Admin"):
2  print("Hi " + user)

```

## Further Reading

  - <https://www.owasp.org/index.php/Use_of_hard-coded_password>
* [OpenStack - B107: hardcoded_password_default](https://docs.openstack.org/developer/bandit/plugins/hardcoded_password_funcdef.html)
