Pattern: Use of plain-text for sensitive data

Issue: -

## Description

Plaintext secrets kept in source code or similar media mean sensitive data is exposed to any users/systems with access to the source code.

**Resolution**: Remove plaintext secrets and encrypt them within a secrets manager instead.

## Examples

The following example will fail the general-secrets-no-plaintext-exposure check.

```terraform
 variable "password" {
   description = "The root password for our VM"
   type        = string
   default     = "p4ssw0rd"
 }
 
 resource "evil_corp" "virtual_machine" {
 	root_password = var.password
 }
```

The following example will pass the general-secrets-no-plaintext-exposure check.

```terraform
 variable "password" {
   description = "The root password for our VM"
   type        = string
 }
 
 resource "evil_corp" "virtual_machine" {
 	root_password = var.password
 }
```

## Further reading

- [https://www.terraform.io/docs/state/sensitive-data.html](https://www.terraform.io/docs/state/sensitive-data.html)