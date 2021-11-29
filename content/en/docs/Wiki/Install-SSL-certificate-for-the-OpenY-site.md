### Security

In order to have better SEO and security for the data, processed from the OpenY instance to client's browser it is required to install SSL certificate for the site.
There are a lot of SSL providers, like Network Solutions, Godaddy, AWS, and tons of other, but in this short tutorial we'll cover free service which looks like reliable and free of charge - LetsEncrypt.

### Installation

Full how-to located https://certbot.eff.org/lets-encrypt/ubuntuxenial-apache

On January 24th 2020 OpenY requirements are
 - Ubuntu 16.04
 - PHP 7.2
 - Apache 2

# Steps to follow
 - make a backup of your server just in case
 - Login via SSH to your server as root user ( using sudo is best practice )
 - RUN
```sh
sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository universe
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install certbot python-certbot-apache
```
commands to get certbot installed for your server
 - Generate SSL certificate for your server by running command
```sh
sudo certbot --apache
```
This command will do automatic SSL installation to Apache2 config on a server. In order to do config changes manually run another command
```sh
sudo certbot certonly --apache
```
Above command will do just SSL certificate generation which you'd need to install manually into vhost config of Apache2
 - visit your website by typing `https` instead of `http`. Example of openy.org - type `https://openy.org`