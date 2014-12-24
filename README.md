RasPi-temp
==========

- SSH-Key Authorizazion
-- on the pi:

mkdir ~/.ssh
touch ~/.ssh/authorized_keys
chmod 700 ~/.ssh/
chmod 600 ~/.ssh/authorized_keys
-- if not already created: create a public ssh key on the machine connecting to the Pi
ssh-keygen
cat /home/domenik/.ssh/id_rsa.pub             #paste content into the raspberries cat ~/home/domenik/.ssh/id_rsa.pub


- Lighttp-setup
-- on the pi:

sudo apt-get install lighttp
# and follow instructions on /var/www/indxe
The DocumentRoot, which is the directory under which all your HTML files should exist, is set to /var/www.
CGI scripts are looked for in /usr/lib/cgi-bin, which is where Debian packages will place their scripts. You can enable cgi module by using command "lighty-enable-mod cgi".
Log files are placed in /var/log/lighttpd, and will be rotated weekly. The frequency of rotation can be easily changed by editing /etc/logrotate.d/lighttpd.
The default directory index is index.html, meaning that requests for a directory /foo/bar/ will give the contents of the file /var/www/foo/bar/index.html if it exists (assuming that /var/www is your DocumentRoot).
You can enable user directories by using command "lighty-enable-mod userdir"
