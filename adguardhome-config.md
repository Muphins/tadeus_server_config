# Prepare OMV-Compose
## Create a macvlan network
In Services > Compose > Networks > (+)
- Fill:  
  Name: _xxx-macvlan_  
  Select macvlan  
  Select the Parent network: _network interface_  
  choose a subnet  
  enter the Gateway  
  **Save**
## create the compose file
