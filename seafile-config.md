# access via https
In ./seafile/conf/seahub_settings.py, add:
CSRF_TRUSTED_ORIGINS = ["https://seafile.example.com"]

In the admin parameters, set SERVICE_URL and FILE_SERVER_ROOT

# Enable webdav
In ./seafile/conf/seafdav.conf
Change enabled to true
