Pattern: Use of sensitive credentials for Azure virtual machine

Issue: -

## Description

When creating Azure Virtual Machines, `custom_data` is used to pass start up information into the EC2 instance. This `custom_data` must not contain access key credentials.

**Resolution**: Don't use sensitive credentials in the VM `custom_data`.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_virtual_machine" "bad_example" {
	name = "bad_example"
	custom_data =<<EOF
export DATABASE_PASSWORD=\"SomeSortOfPassword\"
EOF
}
```

Example of **correct** code:

```terraform
resource "azurerm_virtual_machine" "good_example" {
	name = "good_example"
	custom_data =<<EOF
export GREETING="Hello there"
EOF
}
```