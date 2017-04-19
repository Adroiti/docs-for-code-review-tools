Pattern: Use of hard-coded password function arguments

Issue: -

## Description

The use of hard-coded passwords increases the possibility of password guessing
tremendously. This rule looks for all function calls being passed a
keyword argument that is a string literal. It checks that the assigned local
variable does not look like a password.

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

>> Issue: [B106:hardcoded_password_funcarg] Possible hardcoded
password: 'blerg'
   Severity: Low   Confidence: Medium
   Location: ./examples/hardcoded-passwords.py:16
15
16doLogin(password="blerg")

```

## Further Reading

  - <https://www.owasp.org/index.php/Use_of_hard-coded_password>
* [OpenStack - B106: hardcoded_password_funcarg](https://docs.openstack.org/developer/bandit/plugins/hardcoded_password_funcarg.html)
