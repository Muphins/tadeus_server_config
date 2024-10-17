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
In OMV's shell, create a new bridge to allow connections to the macvlan from br0:
```
ip link add adguard-host link br0 type macvlan mode bridge
ip addr add 192.168.0.14/32 dev adguard-br0
ip link set adguard-br0 up
ip route add 192.168.0.12/30 dev adguard-br0
```
Make the config persitant on reboot:
```
nano /etc/network/interfaces.d/99-adguard-br0
```
```
auto adguard-br0
iface adguard-br0 inet static
    pre-up ip link add adguard-br0 link br0 type macvlan mode bridge
    address 192.168.0.14/32
    up ip link set adguard-br0 up
    up ip route add 192.168.0.12/30 dev adguard-br0
```
## create the compose file
