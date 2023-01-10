# What is VPC

![vpcc](vpcc.png)

Amazon Virtual Private Cloud (Amazon VPC) enables you to launch AWS resources into a virtual network that you've defined. 

 - You have complete control over your virtual networking environment, including a selection of your IP address range, the creation of subnets, and configuration of route tables and network gateways.

- You can easily customize the network configuration for your Amazon Virtual Private Cloud. For example, you can create a public-facing subnet for web servers that can access to the internet and can also place your backend system such as databases or application servers to a private-facing subnet.

- You can provide multiple layers of security, including security groups and network access control lists, to help control access to Amazon EC2 instances in each subnet.

## Features
The following features help you configure a VPC to provide the connectivity that your applications need:

### Virtual private clouds (VPC)
A VPC is a virtual network that closely resembles a traditional network that you'd operate in your own data center. After you create a VPC, you can add subnets.

### Subnets
A subnet is a range of IP addresses in your VPC. A subnet must reside in a single Availability Zone. After you add subnets, you can deploy AWS resources in your VPC.

### IP addressing
You can assign IPv4 addresses and IPv6 addresses to your VPCs and subnets. You can also bring your public IPv4 and IPv6 GUA addresses to AWS and allocate them to resources in your VPC, such as EC2 instances, NAT gateways, and Network Load Balancers.

### Routing
Use route tables to determine where network traffic from your subnet or gateway is directed.

### Gateways and endpoints
A gateway connects your VPC to another network. For example, use an internet gateway to connect your VPC to the internet. Use a VPC endpoint to connect to AWS services privately, without the use of an internet gateway or NAT device.

### Private IP addresses
IP addresses not reachable over the internet are defined as private. Private IPs enable communication between instances in the same network. When you launch a new instance, a private IP address is assigned, and an internal DNS hostname allocated to resolves to the private IP address of the instance. If you want to connect to this from the internet, it will not work. You would need a public IP address for that.

 ### Public IP addresses
Public IP addresses are used for communication between other instances on the internet and yours. Each instance with a public IP address is assigned an external DNS hostname too. Public IP addresses linked to your instances are from Amazon's list of public IPs. On stopping or terminating your instance, the public IP address gets released, and a new one is linked to the instance when it restarts. For retention of this public IP address even after stoppage or termination, an elastic IP address needs to be used.

### Elastic IP Addresses
Elastic IP addresses are static or persistent public IPs that come with your account. If any of your software or instances fail, they can be remapped to another instance quickly with the elastic IP address. An elastic IP address remains in your account until you choose to release it. A charge is associated with an Elastic IP address if it is in your account, but not allocated to an instance.


Amazon VPC provides features that you can use to increase and monitor the security for your VPC:

- Security groups — Act as a firewall for associated Amazon EC2 instances, controlling both inbound and outbound traffic at the instance level
- Network access control lists (ACLs) — Act as a firewall for associated subnets, controlling both inbound and outbound traffic at the subnet level
- Flow logs — Capture information about the IP traffic going to and from network interfaces in your VPC

When you launch an instance in a VPC, you can associate one or more security groups that you’ve created. Each instance in your VPC could belong to a different set of security groups. If you don’t specify a security group when you launch an instance, the instance automatically belongs to the default security group for the VPC.
### Load Balancing
Load balancing in cloud computing distributes traffic and workloads to ensure that no single server or machine is under-loaded, overloaded, or idle. Load balancing optimizes various constrained parameters such as execution time, response time, and system stability to improve overall cloud performance.

### NAT Gateway
A NAT gateway must be launched in a public subnet because it needs internet connectivity. It also requires an elastic IP address, which you can select at the time of launch. Once created, you need to update the route table associated with your private subnet to point internet-bound traffic to the NAT gateway. This way, the instances in your private subnet can communicate with the internet.


### ***Steps involved in solving the task:***

1. start with creating a vpc with private and public subnets
Open the Amazon VPC console and navigate to the VPC Dashboard, choose Launch VPC Wizard. Click on the `Create VPC` button whih is on the top left corner of the VPC Dashboard.
