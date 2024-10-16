From this guide: https://wiki.omv-extras.org/doku.php?id=omv7:omv7_plugins:docker_compose#how_to_create_a_vlan_pi-hole_adguard
# Prepare OMV-Compose
## Create a macvlan network
In Services > Compose > Networks > (+)
- Fill:  
  Name: _xxx-macvlan_  
  Select macvlan  
  Select the Parent network: _network interface_  
  Enter local net's subnet  
  Enter local net's Gateway
  Enter an aux ip for the host server: host=192.168.x.x
  **Save**
## Create a new ip link to the macvlan
In OMV's shell:
```$ ip link add adguard-host link br0 type macvlan mode bridge

## create the compose file
