
**different versions of PHP using Virtual Hosts or .htaccess**
```
sudo a2enmod actions fcgid alias proxy_fcgi
```

1. copy the virtual host default file

```
cp 000-default.conf example.com.conf
```

2. Add code below
```
<VirtualHost *:80>
	ServerAdmin admin@example.com
	ServerName example.com
	DocumentRoot /var/www/html/example.com
	<Directory /var/www/html/example.com>
            Options Indexes FollowSymLinks MultiViews
            AllowOverride All
            Order allow,deny
            allow from all
            Require all granted
	</Directory>
	<FilesMatch \.php>
            SetHandler "proxy:unix:/var/run/php/php8.1-fpm.sock|fcgi://localhost/"
        </FilesMatch>

	ErrorLog ${APACHE_LOG_DIR}/error.log
	CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

3. check syntax
```
sudo apachectl -t
```

4. Enable site
```
sudo a2ensite example.com
```

5. Restart apache2
```
sudo service apache2 restart
sudo systemctl restart apache2

```
