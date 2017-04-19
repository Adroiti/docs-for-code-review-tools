Pattern: Not auto escaping in jinja2

Issue: -

## Description

Jinja2 is a Python HTML templating system. It is typically used to build web
applications, though appears in other places well, notably the Ansible
automation system. When configuring the Jinja2 environment, the option to use
autoescaping on input can be specified. When autoescaping is enabled, Jinja2
will filter input strings to escape any HTML content submitted via template
variables. Without escaping HTML input the application becomes vulnerable to
Cross Site Scripting (XSS) attacks.

Unfortunately, autoescaping is False by default. Thus this rule will
warn on omission of an autoescape setting, as well as an explicit setting of
false. A HIGH severity warning is generated in either of these scenarios.

Example of **incorrect** code:

```python

>> Issue: Using jinja2 templates with autoescape=False is dangerous and can
lead to XSS. Use autoescape=True to mitigate XSS vulnerabilities.
   Severity: High   Confidence: High
   Location: ./examples/jinja2_templating.py:11
10  templateEnv = jinja2.Environment(autoescape=False,
loader=templateLoader)
11  Environment(loader=templateLoader,
12  load=templateLoader,
13  autoescape=False)
14

>> Issue: By default, jinja2 sets autoescape to False. Consider using
autoescape=True to mitigate XSS vulnerabilities.
   Severity: High   Confidence: High
   Location: ./examples/jinja2_templating.py:15
14
15  Environment(loader=templateLoader,
16  load=templateLoader)
17

```

## Further Reading

  - [OWASP XSS](https://www.owasp.org/index.php/Cross-site_Scripting_\(XSS\))
  - <https://realpython.com/blog/python/primer-on-jinja-templating/>
  - <http://jinja.pocoo.org/docs/dev/api/#autoescaping>
  - <https://security.openstack.org/guidelines/dg_cross-site-scripting-xss.html>
* [OpenStack - B701: jinja2_autoescape_false](https://docs.openstack.org/developer/bandit/plugins/jinja2_autoescape_false.html)
