Pattern: Use of hard-coded `auth.User`

Issue: -

## Description

Use `settings.AUTH_USER_MODEL` instead.

Example of **incorrect** code:


```python
class PullRequest(models.Model):
    author = models.ForeignKey("auth.User", models.CASCADE)  # [hard-coded-auth-user]
```