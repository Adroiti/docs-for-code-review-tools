Pattern: RDP access should not be accessible from the Internet, should be blocked on port 3389

Issue: -

## Description

RDP access can be configured on either the network security group or in the network security group rule.

RDP access should not be permitted from the internet (*, 0.0.0.0, /0, internet, any). Consider using the Azure Bastion Service.

**Resolution**: Block RDP port from internet.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_network_security_rule" "bad_example" {
     name                        = "bad_example_security_rule"
     direction                   = "Inbound"
     access                      = "Allow"
     protocol                    = "TCP"
     source_port_range           = "*"
     destination_port_range      = ["3389"]
     source_address_prefix       = "*"
     destination_address_prefix  = "*"
}

resource "azurerm_network_security_group" "example" {
  name                = "tf-appsecuritygroup"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  
  security_rule {
	 source_port_range           = "any"
     destination_port_range      = ["3389"]
     source_address_prefix       = "*"
     destination_address_prefix  = "*"
  }
}
```

Example of **correct** code:

```terraform
resource "azurerm_network_security_rule" "good_example" {
     name                        = "good_example_security_rule"
     direction                   = "Inbound"
     access                      = "Allow"
     protocol                    = "TCP"
     source_port_range           = "*"
     destination_port_range      = ["3389"]
     source_address_prefix       = "4.53.160.75"
     destination_address_prefix  = "*"
}

resource "azurerm_network_security_group" "example" {
  name                = "tf-appsecuritygroup"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  
  security_rule {
	 source_port_range           = "any"
     destination_port_range      = ["3389"]
     source_address_prefix       = "4.53.160.75"
     destination_address_prefix  = "*"
  }
}
```