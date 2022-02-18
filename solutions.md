-Difference between router and switch devices?

- router => is a switching device for networks, that connects two or more packet-switched networks or subnetworks. 

It serves two primary functions: 

    - managing traffic between these networks by forwarding data packets to their intended IP addresses, 
    - allowing multiple devices to use the same Internet connection.

- switch => is a networking device operating at layer 2 or a data link layer of the OSI model. 
it connect devices in a network and use packet switching to send, receive or forward data packets or data frames over the network.

-What is the routing table?

- A routing table is a set of rules, often viewed in table format, that is used to determine where data packets traveling over an Internet Protocol (IP) network will be directed. 
All IP-enabled devices, including routers and switches, use routing tables.


-What is the difference between public and private IP?

- public IP => These are public (global) addresses that are used on the Internet. 
A public IP address is an IP address that is used to access the Internet. Public IP addresses can be routed on the Internet, unlike private addresses.
The presence of a public IP address on your router or computer will allow you to organize your own server (VPN, FTP, WEB, etc.), remote access to your computer, video surveillance cameras, and get access to them from anywhere on the global network.
With a public IP address, you can set up any home server to publish it on the Internet: Web (HTTP), VPN (PPTP/IPSec/OpenVPN, WireGuard), media (audio/video), FTP, NAS, game server, etc.

- private IP => Private (internal) addresses are not routed on the Internet, and no traffic can be sent to them from the Internet; they are only supposed to work within the local network.
Private addresses include IP addresses from the following subnets:
    - Range from 10.0.0.0 to 10.255.255.255 — a 10.0.0.0 network with a 255.0.0.0 or /8 (an 8-bit) mask
    - Range from 172.16.0.0 to 172.31.255.255 — a 172.16.0.0 network with a 255.240.0.0 or /12
    - A 192.168.0.0 to 192.168.255.255 range, which is a 192.168.0.0 network masked by 255.255.0.0 or /16
    - A special range 100.64.0.0 to 100.127.255.255 with a 255.192.0.0 or /10 network mask; this subnet is recommended according to rfc6598 for use as an address pool for CGN (Carrier-Grade NAT)
Those are reserved IP addresses. These addresses are intended for use in closed local area networks, and no one globally controls the allocation of such addresses.

-Difference between public and private subnets?

public subnets => will be used for instances that need a public IP to be accessible from the internet. 
The way we make it a public subnet is to associate a custom route table and add a route to the internet, with an internet gateway as a target. 
Notice that the internet is defined with CIDR notation as 0.0.0.0/0. 
An internet gateway must first be attached to your VPC. 
If you don't have an internet gateway attached to your VPC, none of your instances will be able to reach the internet

private subnets => is used for instances that do not need to be directly reachable from the internet. 
For the best security, it's important to keep backend instances and databases private, so those would go in a private

-Threat-mitigation methods?

1- Conduct a risk assessment to determine vulnerabilities

2- Establish network access controls

3- Implement firewalls and antivirus software

4- Create a patch management schedule

5- Continuously monitor network traffic

6- Build an incident response plan


## Refrences
- [*What is a router?*](https://www.cloudflare.com/learning/network-layer/what-is-a-router/#:~:text=A%20router%20is%20a%20device,use%20the%20same%20Internet%20connection.).
- [*What are Switches*](https://www.tutorialspoint.com/what-are-switches-in-computer-network#:~:text=Switches%20are%20networking%20devices%20operating,which%20computers%20are%20plugged%20in.).
- [*Routing Tables*](https://www.geeksforgeeks.org/routing-tables-in-computer-network/)
- [*What is the difference between a public and private IP address?*](https://help.keenetic.com/hc/en-us/articles/213965789-What-is-the-difference-between-a-public-and-private-IP-address-)
- [*Difference between public and private subnets*](https://www.oreilly.com/library/view/designing-aws-environments/9781789535549/fa751615-4bb5-4d85-b1a7-00808ec69533.xhtml)
- [*Risk Mitigation*](https://securityscorecard.com/blog/6-strategies-for-cybersecurity-risk-mitigation)
