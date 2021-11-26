Pattern: Disabled Threat Detection policy for MySQL database

Issue: -

## Description

Threat detection helps prevent compromise by alerting on threat detections.

**Resolution**: enable threat detection on MySQL database.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_mysql_server" "bad_example" {
  name                = "bad_example"

  public_network_access_enabled    = true
  ssl_enforcement_enabled          = false
  ssl_minimal_tls_version_enforced = "TLS1_2"

  threat_detection_policy {
    enabled = false
  }
}
```

Example of **correct** code:

```terraform
resource "azurerm_mysql_server" "good_example" {
  name                = "good_example"

  public_network_access_enabled    = false
  ssl_enforcement_enabled          = false
  ssl_minimal_tls_version_enforced = "TLS1_2"

  threat_detection_policy {
    enabled = true
  }
}
```