Pattern: Disabled auto upgrade for Kubernetes cluster

Issue: -

## Description

Not running the latest security patches on your Kubernetes cluster can make it a target for penetration.

**Resolution**: Set maintenance policy deterministically when auto upgrades are enabled.

## Examples

The following example will fail the digitalocean-compute-kubernetes-auto-upgrades-not-enabled check.

```terraform
resource "digitalocean_kubernetes_cluster" "foo" {
	name    	 = "foo"
	region  	 = "nyc1"
	version 	 = "1.20.2-do.0"
	auto_upgrade = false

	node_pool {
		name       = "autoscale-worker-pool"
		size       = "s-2vcpu-2gb"
		auto_scale = true
		min_nodes  = 1
		max_nodes  = 5
	}
}
```

The following example will pass the digitalocean-compute-kubernetes-auto-upgrades-not-enabled check.

```terraform
resource "digitalocean_kubernetes_cluster" "foo" {
	name    	 = "foo"
	region  	 = "nyc1"
	version 	 = "1.20.2-do.0"
	auto_upgrade = true

	node_pool {
		name       = "autoscale-worker-pool"
		size       = "s-2vcpu-2gb"
		auto_scale = true
		min_nodes  = 1
		max_nodes  = 5
	}
}
```

## Further reading

- [https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/kubernetes_cluster#auto-upgrade-example](https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/kubernetes_cluster#auto-upgrade-example)
- [https://docs.digitalocean.com/products/kubernetes/resources/best-practices/](https://docs.digitalocean.com/products/kubernetes/resources/best-practices/)