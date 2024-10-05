# Apache

Apache file server with basic auth
```
/etc/apache2/sites-enabled/000-default.conf 
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/archive
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined

    <Directory "/var/archive">
        AuthType Basic
        AuthName "Restricted Content"
        AuthUserFile /etc/apache2/.htpasswd
        Require valid-user
        Options Indexes # mandatory to access and list files
    </Directory>
</VirtualHost>
```

Generate password
```
sudo htpasswd -c /etc/apache2/.htpasswd admin
```
