Pattern: Potentially sensitive data stored in local value

Issue: -

## Description

Sensitive attributes such as passwords and API tokens should not be available in your templates, especially in a plaintext form. You can declare variables to hold the secrets, assuming you can provide values for those variables in a secure fashion. Alternatively, you can store these secrets in a secure secret store, such as AWS KMS.

*NOTE: It is also recommended to store your Terraform state in an encrypted form.*

**Resolution**: Don't include sensitive data in locals.

## Examples

Example of **incorrect** code:

```terraform
locals {
  password = "p4ssw0rd"
}

resource "evil_corp" "bad_example" {
	root_password = local.password
}
```

Example of **correct** code:

```terraform
variable "password" {
  description = "The root password for our VM"
  type        = string
}

resource "evil_corp" "good_example" {
	root_password = var.password
}
```