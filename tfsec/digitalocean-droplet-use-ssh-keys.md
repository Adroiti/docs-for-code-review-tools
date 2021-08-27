Pattern: Missing use of SSH Keys for login

Issue: -

## Description

When working with a server, you’ll likely spend most of your time in a terminal session connected to your server through SSH. A more secure alternative to password-based logins, SSH keys use encryption to provide a secure way of logging into your server and are recommended for all users.

**Resolution**: Use ssh keys for login.

## Examples

Example of **incorrect** code:

```terraform
resource "digitalocean_droplet" "good_example" {
	image    = "ubuntu-18-04-x64"
	name     = "web-1"
	region   = "nyc2"
	size     = "s-1vcpu-1gb"
 }
```

Example of **correct** code:

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