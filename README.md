# Udacity Linux Server Configuration Project

This is the project from Full Stack Nanodegree program from Udacity.

To visit the deployed project, please click here: <http://52.15.197.35>

## Tasks

1. Launch your Virtual Machine
2. Follow the instructions provided to SSH into your server
3. Create a new user called `grader`
4. Give the grader the permission to `sudo`
5. Update all currently installed packages from the VM
6. Change the SSH port from 22 to 2200
7. Configure the UFW to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123)
8. Install and configure Apache to work with Python mod_wsgi application, using Django Framework
9. Install git, clone and setup your Item Catalog project (from <https://github.com/vrbarros/UdacityItemCatalog>) so that it functions correctly when visiting your server's IP address in a browser

# Virtual Machine

## SSH access to the instance

1. Use the Private Key from this project (it is available in PEM or PPK if using PuTTY)
2. Connect to 52.15.197.35 using `ssh` or PuTTY application

## Summary of the software installed

It was important to run `sudo apt-get update` and `sudo apt-get -y upgrade` to update all packages already installed.

1. apache2
2. libapache2-mod-wsgi
3. postgresql
4. python3
5. python3-pip
6. build-essential
7. libssl-dev
8. libffi-dev
9. python-dev
10. python3-venv
11. git

# Configurations made

1. Create `grader` user using `sudo adduser grader`
2. Gave sudo access to `grader` editing sudoers.d directory
3. Set the same public key used by Lightsail user management to Ubuntu
4. Removed `root` access, allowing only `grader`
5. Edit '/etc/ssh/sshd_config' file to force SSH log in and to change default SSH port from 22 to 2200
6. Setup `ufw` allowing ports 80, 123 and 2200
7. Create a project folder in '/var/www' named 'itemscatalog'
8. Cloned project UdacityItemCatalog to 'itemscatalog'
9. Edit '/etc/apache2/sites-available/000-default.conf' and add all configurations needed to run the application
10. The application has a local envinroment to manage the packages in '/var/www/itemscatalog/env'
