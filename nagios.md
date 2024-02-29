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


# Download Nagios and the Plugins

Create a directory for storing the downloads.
```sh
mkdir ~/downloads
cd ~/downloads
```
Download the source code tarballs of both Nagios Core and the Nagios plugins (visit https://www.nagios.org/download/ for links to the latest versions). These directions were tested with Nagios 4.2.1 and Nagios Plugins 2.1.3.
```sh
wget http://prdownloads.sourceforge.net/sourceforge/nagios/nagios-4.2.1.tar.gz
wget http://prdownloads.sourceforge.net/sourceforge/nagiosplug/nagios-plugins-2.1.3.tar.gz
```
# Compile and Install Nagios Core

Extract the Nagios Core source code tarball.
```sh
cd ~/downloads
tar xzf nagios-4.2.1.tar.gz
cd nagios-4.2.1
```
 Run the Nagios configure script, passing the name of the group you created earlier like so:
```sh
./configure --with-command-group=nagcmd
```
Compile the Nagios Core source code.
```sh
make all
```
Install binaries, init script, sample config files and set permissions on the external command directory.
```sh
make install
make install-init
make install-config
make install-commandmode
```
Don't start Nagios Core yet - there's still more that needs to be done... 


# Customize Configuration

Sample configuration files have now been installed in the /usr/local/nagios/etc directory. These sample files should work fine for getting started with Nagios Core. You'll need to make just one change before you proceed ...

Edit the /usr/local/nagios/etc/objects/contacts.cfg config file with your favorite editor and change the email address associated with the nagiosadmin contact definition to the address you'd like to use for receiving alerts.
```sh
vi /usr/local/nagios/etc/objects/contacts.cfg
```
# Configure the Web Interface

Install the Nagios Core web config file in the Apache conf.d directory.
```sh
make install-webconf
```
Create a nagiosadmin account for logging into the Nagios Core web interface. Remember the password you assign to this account - you'll need it later.
```sh
htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin
```
Restart Apache to make the new settings take effect.
```sh
/etc/init.d/apache2 reload
```


# Compile and Install the Nagios Plugins

Extract the Nagios plugins source code tarball.
```sh
cd ~/downloads
tar xzf nagios-plugins-2.1.3.tar.gz
cd nagios-plugins-2.1.3
```
Compile and install the plugins.
```sh
./configure --with-nagios-user=nagios --with-nagios-group=nagios
make
make install
```


# Start Nagios Core

Configure Nagios Core to automatically start when the system boots.
```sh
ln -s /etc/init.d/nagios /etc/rcS.d/S99nagios
```
Verify the sample Nagios Core configuration files.
```sh
/usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg
```
If there are no errors, start Nagios Core.
```sh
/etc/init.d/nagios start
```

# Login to the Web Interface

You should now be able to access the Nagios Core web interface at the URL below. You'll be prompted for the username (nagiosadmin) and password you specified earlier.
```sh
http://localhost/nagios/
```
Click on the "Service Detail" navbar link to see details of what's being monitored on your local machine. It will take a few minutes for Nagios Core to check all the services associated with your machine, as the checks are spread out over time.

# Other Modifications

If you want to receive email notifications for Nagios Core alerts, you need to install the mailx (Postfix) package.
```sh
sudo apt-get install mailx
sudo apt-get install postfix
```
You'll have to edit the Nagios Core email notification commands found in /usr/local/nagios/etc/objects/commands.cfg and change any '/bin/mail' references to '/usr/bin/mail'. Once you do that you'll need to restart Nagios Core to make the configuration changes live.
```sh
sudo /etc/init.d/nagios restart
```
Configuring email notifications is outside the scope of this documentation. Refer to your system documentation, search the web, or look to the Nagios Support Portal or Nagios Community Wiki for specific instructions on configuring your Ubuntu system to send email messages to external addresses.



