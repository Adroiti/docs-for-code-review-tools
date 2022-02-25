Pattern: Missing use of Standard subscription tier for Azure Defender

Issue: -

## Description

To benefit from Azure Defender you should use the Standard subscription tier. Enabling Azure Defender extends the capabilities of the free mode to workloads running in private and other public clouds, providing unified security management and threat protection across your hybrid cloud workloads.

**Resolution**: Enable standard subscription tier to benefit from Azure Defender.

## Examples

The following example will fail the azure-security-center-enable-standard-subscription check.
```terraform

 resource "azurerm_security_center_subscription_pricing" "bad_example" {
   tier          = "Free"
   resource_type = "VirtualMachines"
 }
 
```

The following example will pass the azure-security-center-enable-standard-subscription check.
```terraform

 resource "azurerm_security_center_subscription_pricing" "good_example" {
   tier          = "Standard"
   resource_type = "VirtualMachines"
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/security_center_subscription_pricing#tier](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/security_center_subscription_pricing#tier)
- [https://docs.microsoft.com/en-us/azure/security-center/security-center-pricing](https://docs.microsoft.com/en-us/azure/security-center/security-center-pricing)