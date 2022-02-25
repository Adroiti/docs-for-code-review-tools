Pattern: Disabled alert notifications for Azure Security Center

Issue: -

## Description

It is recommended that at least one valid contact is configured for the security center. 
Microsoft will notify the security contact directly in the event of a security incident using email and require alerting to be turned on.

**Resolution**: Set alert notifications to be on.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_security_center_contact" "bad_example" {
  email = "bad_example@example.com"
  phone = "+1-555-555-5555"

  alert_notifications = false
  alerts_to_admins    = false
}
```

Example of **correct** code:

```terraform
resource "azurerm_security_center_contact" "good_example" {
  email = "good_example@example.com"
  phone = "+1-555-555-5555"

  alert_notifications = true
  alerts_to_admins    = true
}
```