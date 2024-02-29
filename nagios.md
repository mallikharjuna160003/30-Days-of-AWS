# Nagios Monitoring tool
- Launch an EC2 instance two instances 1 ec2 name it as nagios other as Client.
- Create a Key-Pair
- Choose both as Ubuntu Amazon Machine Image.

  
![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/4ad83904-81e5-43b9-ac45-2678cf1c0a27)

# installing Nagios on nagios ec2 
- ssh to the nagios ec2 via key-pair .pem file
- Do the `sudo su` for root user
  ```sh
  sudo apt-get install apache2 libapache2-mod-php5 build-essential libgd-dev
  ```
  ) Create Account Information

Become the root user.

sudo -s

# Create a new nagios user account and give it a password.
```sh
/usr/sbin/useradd -m -s /bin/bash nagios
passwd nagios
```
You will need to also add a nagios group (if it's not created by default).
```sh
/usr/sbin/groupadd nagios
/usr/sbin/usermod -G nagios nagios
```
Create a new nagcmd group for allowing external commands to be submitted through the web interface. Add both the nagios user and the apache user to the group.
```sh
/usr/sbin/groupadd nagcmd
/usr/sbin/usermod -a -G nagcmd nagios
/usr/sbin/usermod -a -G nagcmd www-data
```
