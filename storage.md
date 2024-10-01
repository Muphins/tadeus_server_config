# Clean old raid disks
Tips for mdadm raid volumes:  
It seems impossible to delete a raid volume that was not created within OMV. I had to delete the partitions headers with the command $ dd if=/dev/zero of=/dev/mdX  
Interrupt the command (CTRL+C) after a few seconds (I did 45-ish)

# Create HDD ZFS pool
- In "Storage>Disks" erase all the required disks
- Identify the disks (/dev/sdX)
- "Storage > ZFS > Pools > Add pool"
  - name the pool "hdd_pool" (no capitals)
  - no mount point
  - by ID
  - Force creation if disks are of different sizes
- Apply changes

# Add seafile user's libraries as external webdav filesystems
- install add-on "openmediavault-remotemount 7.0.2"
- In Storage > Remote Mount, create a new DAVFS mount point  
  Server= localhost:8080/seafdav  
New mount is located at /srv/remotemount/mountname
