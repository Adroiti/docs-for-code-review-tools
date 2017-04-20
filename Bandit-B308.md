Pattern: Use of `mark_safe()`

Issue: -

## Description

Use of Django's `mark_safe() `may expose cross-site scripting vulnerabilities and should be reviewed.

It is also important to be particularly careful when using `is_safe` with custom template tags, the `safe` template tag, `mark_safe`, and when autoescape is turned off.

## Further Reading

* [django - Security in Django](https://docs.djangoproject.com/en/1.11/topics/security/)
* [django - mark_safe](https://docs.djangoproject.com/en/1.11/ref/utils/#django.utils.safestring.mark_safe)
* [OpenStack - B308: mark_safe](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b308-mark-safe)
