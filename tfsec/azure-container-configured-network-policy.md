Pattern: Ensure AKS cluster has Network Policy configured

Issue: -

## Description

The Kubernetes object type NetworkPolicy should be defined to have opportunity allow or block traffic to pods, as in a Kubernetes cluster configured with default settings, all pods can discover and communicate with each other without any restrictions.

**Resolution**: Configure a network policy.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_kubernetes_cluster" "bad_example" {
	network_profile {
	  }
}
```

Example of **correct** code:

```terraform
resource "azurerm_kubernetes_cluster" "good_example" {
	network_profile {
	  network_policy = "calico"
	  }
}
```