# az-pi-hole
Running Pi-Hole on Azure


![alt text](./img/diagram.jpg)

<!-- ```plantuml
@startuml

!define C4Puml https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master
!define AzurePuml https://raw.githubusercontent.com/plantuml-stdlib/Azure-PlantUML/master/dist
'!define AzurePuml https://raw.githubusercontent.com/plantuml-stdlib/Azure-PlantUML/release/2-1/dist

!includeurl C4Puml/C4_Context.puml
!includeurl C4Puml/C4_Component.puml
!includeurl C4Puml/C4_Container.puml

!includeurl AzurePuml/AzureCommon.puml

' Azure Resources
!includeurl AzurePuml/Compute/AzureVirtualMachine.puml
!includeurl AzurePuml/Networking/AzureBastion.puml
!includeurl AzurePuml/Networking/AzureLoadBalancer.puml
!includeurl AzurePuml/Networking/AzurePublicIPAddress.puml
!includeurl AzurePuml/Networking/AzureNSG.puml

'left to right direction

title Example Multi Cloud PlantUML C4 Diagram

AzureVirtualMachine(client,"client","")
Boundary(azure,"subscription") {
	Boundary(azurerg,"rg-phdns-westeu") {
		Boundary(azurevn,"vnet-westeu", "10.1.0.0/16") {
            Boundary(snetbastion,"snet-bst-westeu", "10.1.3.0/24") {
                AzureBastion(bst, "bst-westeu-1", "Bastion Host")
            }
			Boundary(snetvms,"snet-dns-westeu", "10.1.1.0/24") {
                AzureVirtualMachine(jumphost, "vm-jh-westeu-1", "Jumphost,Standard B1s")
				AzureVirtualMachine(dns1, "vm-dns-westeu-1", "Pi-Hole DNS 1,Standard B1s")
                AzureVirtualMachine(dns2, "vm-dns-westeu-2", "Pi-Hole DNS 2,Standard B1s")
			}
			Boundary(azurelb,"snet-lb-westeu", "10.1.2.0/24") {
                AzureNSG(nsg1, "nsg-dnsallow-1", "Network Security Group")
				AzureLoadBalancer(alb, "lb-westeu-1", "Azure Load Balancer")
			}
		}
        AzurePublicIPAddress(pip, "pip-lb-westeu-1", "Azure Public IP")
	}
}

Rel_R(client, pip, "TCP/UDP (53)")
Rel_R(pip, alb, " ")
Rel_R(bst, jumphost, " ")
Rel_R(alb, dns1, " ")
Rel_R(alb, dns2, " ")


@enduml
``` -->
