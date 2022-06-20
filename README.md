# About
This is a wrapper-script for NetworkManagers OpenConnect helper, that routes adresses provided by Ciscos ASA as excludes through other default routes.
# installation

Run the following to divert the real helper:
``` sh
sudo dpkg-divert --add --rename --divert \
/usr/lib/NetworkManager/nm-openconnect-service-openconnect-helper.real \
/usr/lib/NetworkManager/nm-openconnect-service-openconnect-helper
```
Then copy over this wrappers-script to `/usr/lib/NetworkManager/nm-openconnect-service-openconnect-helper`

The following entry is needed in the sudoers file to allow nm-openconnect to manage the routes:

``` readline-config
nm-openconnect ALL=NOPASSWD: /usr/sbin/ip
```
