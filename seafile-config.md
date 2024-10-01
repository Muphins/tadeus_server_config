# access via https
In ./seafile/conf/seahub_settings.py, add:
CSRF_TRUSTED_ORIGINS = ["https://seafile.example.com"]

# Enable webdav
In ./seafile/conf/seafdav.conf
Change enabled to true
