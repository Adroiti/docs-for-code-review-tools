Pattern: Use of `Mako` templates

Issue: -

## Description

Mako templates allow HTML/JS rendering by default and are
inherently open to XSS attacks. Ensure variables in all templates are
properly sanitized via the `n`, `h` or `x` flags (depending on context).
For example, to HTML escape the variable `data` do `${ data |h }`.

## Further Reading

* [Mako Templates for Python](http://www.makotemplates.org)
* [OpenStack - Escape user input to prevent XSS attacks](https://security.openstack.org/guidelines/dg_cross-site-scripting-xss.html)
* [OpenStack - B702: use_of_mako_templates](https://docs.openstack.org/developer/bandit/plugins/use_of_mako_templates.html)
