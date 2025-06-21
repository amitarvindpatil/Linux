## Configure php on apapche on linux
============================================================
-`sudo yum update -y`
-`sudo yum install php php-mysqlnd php-cli php-common -y`
-`sudo systemctl restart httpd`
-`php -v`
- Add code into /var/www/sixcolor.academy/info.php `<?php phpinfo(); ?>`
- Run on browser `sixcolor.academy/info.php`

## Configure MySQL linux
============================================================
- `sudo yum update -y`
- `sudu yum install mysql-server -y`
- `sudo systemctl start mysqld`
- `sudo systemctl status mysqld`
- `sudo mysql_secure_installation`
- `mysql -u root -p`
- `mysql> user mysql;`