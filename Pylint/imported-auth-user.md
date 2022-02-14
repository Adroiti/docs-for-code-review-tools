Pattern: User model imported from `django.contrib.auth.models`

Issue: -

## Description

Use `django.contrib.auth.get_user_model()` instead.

Example of **incorrect** code:

```python
from django.contrib.auth.models import *  # [imported-auth-user]
from django.contrib.auth.models import User  # [imported-auth-user]
```