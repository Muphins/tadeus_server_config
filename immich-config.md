#### _Applicable for immich v1.117.0_
# Prepare the container and start
Follow the guide here: https://immich.app/docs/install/docker-compose
### In compose.yml:
- Change immich port to 8002
- If using OMV-Compose, change ".env" to "immich.env" in the "env-files:" sections

### In the Environment section:
- Change UPLOAD_LOCATION=/mnt/immich-data  
  _# ZFS filesystem at this mountpoint shall be created first_
- Change DB_DATA_LOCATION=/docker/app-data/immich
- Change immich version to v1.117.0
# Setup Hardware-Accelerated Machine Learning
Not possible for now
# Setup user account
