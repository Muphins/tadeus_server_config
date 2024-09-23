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
