# Using VM-Series Firewalls, the Azure Application Gateway and Standard ILB to Secure Internet-Facing Web Workloads

Adapted from the [Azure Application Gateway ARM template](https://github.com/PaloAltoNetworks/azure-applicationgateway).

This ARM template deploys two VM-Series firewalls between a pair of Azure load balancers. The external load balancer is an Azure Application Gateway (a web load balancer) that also serves as the Internet facing gateway, which  receives traffic and distributes it to the VM-Series firewalls. The firewalls enforce security policies to protect your workloads, and send the allowed traffic to the internal load balancer which is an Azure Load Balancer (Layer 4) that load balances across a pair of sample Apache web servers.  The ILB is utilizes a Standard Preview which can be used with HA Ports for Outbound and East/West traffic.

[Standard Load Balancer](https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-standard-overview)

[HA Ports](https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-ha-ports-overview)

As demand for your web services increase, you can add more web servers and deploy additional VM-Series firewalls for more capacity. The VM-Series firewalls are deployed in separate Availability Sets for higher availability and redundancy against planned and unplanned outages. Refer to Azure documentation for more information on [Availability Sets](https://docs.microsoft.com/en-us/azure/virtual-machines/virtual-machines-linux-manage-availability). A sample configuration file for VM-Series firewall is also included. After you import this configuration file, be sure to (a) customize the security policies to your needs and (b) <b>set a custom password</b> for the firewall instead of the value in the sample file. Refer to the documentation for steps on how to import the sample configuration file. 

**Documentation**
* Release Notes: Included in this repository.
* About the [VM-Series Firewall for Azure](https://azure.paloaltonetworks.com)

[<img src="http://azuredeploy.net/deploybutton.png"/>](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjasonmeurer%2Fazure-applicationgateway%2Fmaster%2Fazuredeploy.json)
