Pattern: Missing telephone number for Azure security center

Issue: -

## Description

It is recommended that at least one valid contact is configured for the security center. 
Microsoft will notify the security contact directly in the event of a security incident and will look to use a telephone number in cases where a prompt response is required.

**Resolution**: Set a telephone number for security center contact.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_security_center_contact" "bad_example" {
  email = "bad_contact@example.com"
  phone = ""

  alert_notifications = true
  alerts_to_admins    = true
}
```

Example of **correct** code:

```terraform
resource "azurerm_security_center_contact" "good_example" {
  email = "good_contact@example.com"
  phone = "+1-555-555-5555"

  alert_notifications = true
  alerts_to_admins    = true
}
```