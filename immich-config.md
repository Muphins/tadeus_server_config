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
- Add IMMICH_TRUSTED_PROXIES=192.168.144.3
- Change immich version to v1.117.0
# Setup Hardware-Accelerated Machine Learning
Not possible for now
# using reverse proxy
Immich login only works with https.  
In administration parameters of immich, set the server's url: "https://immich.example.com"  
Add the following to the advanced tab of nginxProxyManager:
```
# allow large file uploads
client_max_body_size 50000M;

# Set headers
proxy_set_header Host              $http_host;
proxy_set_header X-Real-IP         $remote_addr;
proxy_set_header X-Forwarded-For   $proxy_add_x_forwarded_for;
proxy_set_header X-Forwarded-Proto $scheme;
```
