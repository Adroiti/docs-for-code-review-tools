Pattern: Missing use of SSH keys for DigitalOcean compute

Issue: -

## Description

When working with a server, you’ll likely spend most of your time in a terminal session connected to your server through SSH. A more secure alternative to password-based logins, SSH keys use encryption to provide a secure way of logging into your server and are recommended for all users.

**Resolution**: Use SSH keys for login.

## Examples

The following example will fail the digitalocean-compute-use-ssh-keys check.

```terraform
 resource "digitalocean_droplet" "good_example" {
 	image    = "ubuntu-18-04-x64"
 	name     = "web-1"
 	region   = "nyc2"
 	size     = "s-1vcpu-1gb"
  }
```

The following example will pass the digitalocean-compute-use-ssh-keys check.

```terraform
 data "digitalocean_ssh_key" "terraform" {
 	name = "myKey"
   }
   
 resource "digitalocean_droplet" "good_example" {
 	image    = "ubuntu-18-04-x64"
 	name     = "web-1"
 	region   = "nyc2"
 	size     = "s-1vcpu-1gb"
 	ssh_keys = [ data.digitalocean_ssh_key.myKey.id ]
 }
```

## Further reading

- [https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/droplet#ssh_keys](https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/droplet#ssh_keys)
- [https://www.digitalocean.com/community/tutorials/understanding-the-ssh-encryption-and-connection-process](https://www.digitalocean.com/community/tutorials/understanding-the-ssh-encryption-and-connection-process)