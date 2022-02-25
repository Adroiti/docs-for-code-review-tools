Pattern: Unencrypted Azure managed disk

Issue: -

## Description

Manage disks should be encrypted at rest. When specifying the `encryption_settings` block, the enabled attribute should be set to `true`.

**Resolution**: Enable encryption on managed disks.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_managed_disk" "bad_example" {
	encryption_settings {
		enabled = false
	}
}
```

Example of **correct** code:

```terraform
resource "azurerm_managed_disk" "good_example" {
	encryption_settings {
		enabled = true
	}
}
```