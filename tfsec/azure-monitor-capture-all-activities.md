Pattern: Ensure log profile captures all activities

Issue: -

## Description

Log profiles should capture all categories to ensure that all events are logged

**Resolution**: Configure log profile to capture all activities.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_monitor_log_profile" "bad_example" {
  name = "bad_example"

  categories = []

  retention_policy {
    enabled = true
    days    = 7
  }
}
```

Example of **correct** code:

```terraform
resource "azurerm_monitor_log_profile" "good_example" {
  name = "good_example"

  categories = [
	  "Action",
	  "Delete",
	  "Write",
  ]

  retention_policy {
    enabled = true
    days    = 365
  }
}
```