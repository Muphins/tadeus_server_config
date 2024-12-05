# Access via https
In ./seafile/conf/seahub_settings.py, add:
CSRF_TRUSTED_ORIGINS = ["https://seafile.example.com"]

In the admin parameters, set SERVICE_URL and FILE_SERVER_ROOT

# Allow for large downloads
In Nginx proxy manager, edit seafile proxy host advanced settings. Add:
```
proxy_max_temp_file_size 0;
```
_default cache causes large downloads to fail at around 1GB_

# Enable webdav
In ./seafile/conf/seafdav.conf
Change enabled to true
