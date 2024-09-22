# Install
install OMV7 from USB to SSD  
https://wiki.omv-extras.org/doku.php?id=omv6:new_user_guide#amd64_openmediavault_installation  
# OMV-Extras
install omv extras from https://github.com/OpenMediaVault-Plugin-Developers/installScript/  
install openmediavault-compose 7.2.4 from omv's plugin page  
# Network bridge
(to use OMV PC as a switch)
delete network interface  
add network bridge interface, selecting both NICs and activate IPv4
- set static IP
- set DNS
- save and apply
Edit /etc/systl.conf -> uncomment line "net.ipv4.ip_forward=1"
Reboot
# Kernel & ZFS
https://wiki.omv-extras.org/doku.php?id=omv6:omv6_plugins:kernel
Install openmediavault-kernel add-on
Install Proxmox Kernel 6.5
(as of 2024/09/22, kernel 6.8 causes problems to install updates and packages)
Reboot
Remove other kernels (ticked in column "Removable")
Reboot
In System>OMV Extras -> "Clean APT"
Do updates
Install ZFS addon
# Disks & Health
Activate SMART : https://wiki.omv-extras.org/doku.php?id=omv6:new_user_guide#hard_drive_health_and_smart
# Docker
Install openmediavault-compose from the add-ons menu
https://wiki.omv-extras.org/doku.php?id=omv6:omv6_plugins:docker_compose
