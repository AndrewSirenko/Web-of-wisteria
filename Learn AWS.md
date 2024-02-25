
## Regions & AZs

Region has 3+ AZs

AZ has data centers filled with racks of hosts

## Networking

Learn basics of [[Computer Networking]]

VPC: 
- CIDR block of IPs spanning a region
- VPC has 1+ subnets
- Implicit route between all subnets within a VPC

Subnet:
- spans AZ
- with subset of VPC's IPs 
- Has a routing table
	- Public subnet has a route to internet gateway in routing table. (Otherwise private subnet)

Route Table:
- Set of rules(routes) determining where network traffic is directed
	- Internet/NAT Gateway
	- Gateway endpoint
	- VPC peering / AWS Transit Gateway
	- VPN gateway/Direct connect

Internet Gateway:
- 2-way "Router" between VPC and internet
- Horizontally scaled, redundant, highly available 
- No bandwidth constraints

Elastic IP Address:
- Static IPv4 address associated with AWS account
- Dynamically assigned 
- Locked to region
- Associate with instance or Network interface
- Can be remapped to another instance in account

NAT Gateway:
- Network Address Translation service
- Outbound communication to internet

VPC Endpoint:
- Connect to AWS APIs without public internet 
	- No public IPs or internet connection needed
	- (Powered by AWS PrivateLink)
## Security

80/20 watch DPE Becky's Talk: [AWS re:Inforce 2019: The Fundamentals of AWS Cloud Security (FND209-R)](https://www.youtube.com/watch?v=-ObImxw1PmI&t=1591)


