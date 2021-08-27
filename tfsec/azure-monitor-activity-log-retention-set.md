Pattern: Ensure the activity retention log is set to at least a year

Issue: -

## Description

The average time to detect a breach is up to 210 days, to ensure that all the information required for an effective investigation is available, the retention period should allow for delayed starts to investigating.

**Resolution**: Set a retention period that will allow for delayed investigation.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_monitor_log_profile" "bad_example" {
  name = "bad_example"

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

  retention_policy {
    enabled = true
    days    = 365
  }
}
```