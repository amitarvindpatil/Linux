## Configuration of Virtual Hosting

AWS Linux Server
==================================
- `cd /etc/httd/conf.d`
- `vim sixcolor.academy.conf`

##### add below config

    <VirtualHost *:80>
        ServerName sixcolor.academy
        ServerAlias www.sixcolor.academy
        DocumentRoot /var/www/sixcolor.academy

        ServerAdmin webmaster@sixcolor.academy
        ErrorLog /var/log/httpd/sixcolor_academy_error.log
        CustomLog /var/log/httpd/sixcolor_academy_access.log combined

    RewriteEngine on
    RewriteCond %{SERVER_NAME} = sixcolor.academy [OR]
    RewriteCond %{SERVER_NAME} = www.sixcolor.academy
    RewriteRule ^ https://%{SERVER_NAME}%{REQUEST_URI} {END,NE,R=permanent}
    </VirtualHost>

- `sudo mkdir /var/www/sixcolor.academy`
- `Add HTML Content in /var/www/sixcolor.academy/index.html`
- Set Permission
- `ps -ef | grep httpd` 
- `sudo chown -R apache:apache /var/www/sixcolor.academy`
- `sudo chmod -R 755 /var/www/sixcolor.academy`
- `sudo systemsctl restart httpd`

- Update Host
- `vim /etc/host`
- Add `127.0.0.1 sixcolor.academy`      