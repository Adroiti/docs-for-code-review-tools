Pattern: Use of hard-coded password strings

Issue: -

## Description

The use of hard-coded passwords increases the possibility of password guessing
tremendously. This rule looks for all string literals and checks the
following conditions:

  - assigned to a variable that looks like a password
  - assigned to a dict key that looks like a password
  - used in a comparison with a variable that looks like a password

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

>> Issue: Possible hardcoded password '(root)'
   Severity: Low   Confidence: Low
   Location: ./examples/hardcoded-passwords.py:5
4 def someFunction2(password):
5 if password == "root":
6 print("OK, logged in")

```

## Further Reading

  - <https://www.owasp.org/index.php/Use_of_hard-coded_password>
* [OpenStack - B105: hardcoded_password_string](https://docs.openstack.org/developer/bandit/plugins/hardcoded_password_string.html)