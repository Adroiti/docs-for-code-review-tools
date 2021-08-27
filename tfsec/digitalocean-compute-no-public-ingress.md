Pattern: Firewall has inbound rule with open access

Issue: -

## Description

Opening up ports to connect out to the public internet is generally to be avoided. You should restrict access to IP addresses or ranges that are explicitly required where possible.

**Resolution**: Set a more restrictive CIRDR range.

## Examples

Example of **incorrect** code:

```terraform
resource "digitalocean_firewall" "bad_example" {
	name = "only-22-80-and-443"
  
	droplet_ids = [digitalocean_droplet.web.id]
  
	inbound_rule {
	  protocol         = "tcp"
	  port_range       = "22"
	  source_addresses = ["0.0.0.0/0", "::/0"]
	}
}
```

Example of **correct** code:

```terraform
resource "digitalocean_firewall" "good_example" {
	name = "only-22-80-and-443"
  
	droplet_ids = [digitalocean_droplet.web.id]
  
	inbound_rule {
	  protocol         = "tcp"
	  port_range       = "22"
	  source_addresses = ["192.168.1.0/24", "2002:1:2::/48"]
	}
}
```