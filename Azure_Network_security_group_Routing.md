### Network Security Groups:
- Network Security Groups can be applied to NIC, Subnet or both, Just like firewalls Rules. 
- Restrict inbound & outbound traffic - (IP & Ports).
-  These are state full rules which will have outbound and inbound access separately with out which traffic can't be established.
- Default Rules can't be deleted but can be overwritten to pass the traffic with high priority rules (Rule ID's). 
- Rules are processed according to priority, lower the number hight the priority.
- Once a rule is matched, no further rules are processed. 
- Default Deny all is the rule applied to inbound and Outbound traffic.
- Source IP +Source Port & Destination ip + Destination port, Protocol(TCP/UDP), Action (Allow/Deny)
- Once the security group is created it should be associated with subnet group/NIC Card or both.

### VNet Route :
- We don't need to create routes for different Subnets, as Azure will take of creating routing tables for communication. 
- We can't manage the routing tables created by Azure.
- We can create User Defined routing tables to control our traffic. 
- **Effective Routes** in Nic card tab will help you to see the existing routing tables for that NIC.
- CIDR & priority take the precedence over other table. Ex: 10.1.0.0/16 will have higher & 10.0.0.0/8 will have less precedence.
- Next hop type :
  - Virtual network gateway: - Pushes traffic to VPN for Hybrid Cloud.
  - Virtual Network: - Virtual network inside the Azure cloud. 
  - Internet : - Connect to internet gateways
  - Virtual appliance :- If using virtual machine as appliance or firewall server, we can give IP or VM.
  - None :- Drop the pkt
- Associate routing table to subnet.
- If user defined and Azure routing table are having same CIDR then User Defined routing table will have more preceding. 
  - System generated will go to inactive (Default Invalid 0.0.0.0/0 None)
  - User define goes to Active. (user Active 0.0.0.0/0 None)
  - If BGP is in place then **User defined -> BGP -> System generated ** will take the preceding value.
  
