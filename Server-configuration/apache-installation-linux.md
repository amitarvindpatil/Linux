## Apache2(httpd) installation on AWS Linux Server

- `sudo yum install httpd`
- `sudo systemctl start httpd`
- `sudo systemctl enable httpd`
- `sudo systemctl status httpd`
To Allow HTTP/HTTPS traffic through the Firewall
- `sudo yum install firewalld`
- `sudo systemctl start firewalld`
- `sudo systemctl enable firewalld`
- `sudo firewall-cmd --permanent --add-service-http`
- `sudo firewall-cmd --permanent --add-service-https`
- `sudo firewall-cmd --reload`
- `echo "Welcome to apache webserver" > /var/www/html/index.html` -> test on browser

## Apache2(httpd) installation on Ubantu Server
- `sudo apt update && apt install apache2`
- `sudo systemctl status apache2`
- `sudo systemctl start apache2`
- `sudo systemctl enable apache2`
- `ufw status`  -> firewall check
- `ufw allow 'apache Full'`
- `copy IP address and paste on browser`