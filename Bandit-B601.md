Pattern: Shell injection within Paramiko

Issue: -

## Description

Paramiko is a Python library designed to work with the SSH2 protocol for
secure (encrypted and authenticated) connections to remote machines. It is
intended to run commands on a remote host. These commands are run within a
shell on the target and are thus vulnerable to various shell injection
attacks. Bandit reports a MEDIUM issue when it detects the use of Paramiko's
"exec_command" or "invoke_shell" methods advising the user to check inputs are
correctly sanitized.

Example of **incorrect** code:

```python

>> Issue: Possible shell injection via Paramiko call, check inputs are
   properly sanitized.
   Severity: Medium   Confidence: Medium
   Location: ./examples/paramiko_injection.py:4
3# this is not safe
4paramiko.exec_command('something; reallly; unsafe')
5

>> Issue: Possible shell injection via Paramiko call, check inputs are
   properly sanitized.
   Severity: Medium   Confidence: Medium
   Location: ./examples/paramiko_injection.py:10
9# this is not safe
10   SSHClient.invoke_shell('something; bad; here\n')
11

```

## Further Reading

  - <https://github.com/paramiko/paramiko>
  - <https://www.owasp.org/index.php/Command_Injection>
* [OpenStack - B601: paramiko_calls](https://docs.openstack.org/developer/bandit/plugins/paramiko_calls.html)
