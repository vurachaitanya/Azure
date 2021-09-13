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
