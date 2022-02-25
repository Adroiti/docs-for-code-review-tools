Pattern: Use of HTTP for DigitalOcean compute

Issue: -

## Description

Plain HTTP is unencrypted and human-readable. This means that if a malicious actor was to eavesdrop on your connection, they would be able to see all of your data flowing back and forth.

You should use HTTPS, which is HTTP over an encrypted (TLS) connection, meaning eavesdroppers cannot read your traffic.

**Resolution**: Switch to HTTPS to benefit from TLS security features.

## Examples

The following example will fail the digitalocean-compute-enforce-https check.

```terraform
 resource "digitalocean_loadbalancer" "bad_example" {
   name   = "bad_example-1"
   region = "nyc3"
 
   forwarding_rule {
     entry_port     = 80
     entry_protocol = "http"
 
     target_port     = 80
     target_protocol = "http"
   }
 
   droplet_ids = [digitalocean_droplet.web.id]
 }
```

The following example will pass the digitalocean-compute-enforce-https check.

```terraform
 resource "digitalocean_loadbalancer" "bad_example" {
   name   = "bad_example-1"
   region = "nyc3"
   
   forwarding_rule {
 	entry_port     = 443
 	entry_protocol = "https"
   
 	target_port     = 443
 	target_protocol = "https"
   }
   
   droplet_ids = [digitalocean_droplet.web.id]
 }
```

## Further reading

- [https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/loadbalancer](https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/loadbalancer)
- [https://docs.digitalocean.com/products/networking/load-balancers/](https://docs.digitalocean.com/products/networking/load-balancers/)