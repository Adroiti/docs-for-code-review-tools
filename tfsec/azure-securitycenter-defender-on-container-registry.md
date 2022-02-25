Pattern: Disabled `ContainerRegistry` in Azure Defender

Issue: -

## Description

Azure Defender is a cloud workload protection service that utilizes and agent-based deployment to analyze signals from Azure network fabric and the service control plane, to detect threats across all Azure resources. It can also analyze non-Azure resources, utilizing Azure Arc, including those on-premises and in both AWS and GCP (once they've been onboarded).

Azure Defender for container registries includes a vulnerability scanner to scan the images in Azure Resource Manager-based Azure Container Registry registries and provide deeper visibility image vulnerabilities.

**Resolution**: enable `ContainerRegistry` in Azure Defender.

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
  resource_type = "VirtualMachines,ContainerRegistry"
}
```