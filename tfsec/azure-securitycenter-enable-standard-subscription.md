Pattern: Disabled Standard subscription tier for Azure security center

Issue: -

## Description

To benefit from Azure Defender you should use the Standard subscription tier.
			
Enabling Azure Defender extends the capabilities of the free mode to workloads running in private and other public clouds, providing unified security management and threat protection across your hybrid cloud workloads.

**Resolution**: Enable standard subscription tier to benefit from Azure Defender.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_security_center_subscription_pricing" "bad_example" {
  tier          = "Free"
  resource_type = "VirtualMachines"
}
```

Example of **correct** code:

```terraform
resource "azurerm_security_center_subscription_pricing" "good_example" {
  tier          = "Standard"
  resource_type = "VirtualMachines"
}
```