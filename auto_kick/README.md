# Automated Installation of RHEL6

Before you run RHEL6 OS on network you must configure the server to run with
PXE mode, where your NIC has to support that feature.

DHCP must be configured in your server so that you are able to to offer IP automatically
to the hosts.
```bash
cd /var/lib/tftpboot
```
# Install the right packages
```bash 
yum -y install  dhcp  tftp-server  syslinux  vsftpd  system-config-kickstart
```
# install dhcp and configure it 
``` bash
vim /etc/dhcp/dhcpd.conf
```
configurations can be found in [dhcp]()
``` bash
allow booting;
allow bootp;
authoritative;
filename"pxelinux.0"
```
and comment line 24-44
# configure tftp
``` bash
vim /etc/xinetd.d/tftp

```
in the file disable=no;
# Then copy the RHEL6 files to FTP boot directory
```bash
cp * -vrf /media/RHEL*/   /var/ftp/pub   

cd /media/RHEL*/isolinux

cp * -vrf /var/lib/tftpboot 
cd /var/lib/tftpboot

ls -l
```
to display all content of the tftpboot directory and 
 to show the current working directory using pwd
 
``` bash
mkdir pxelinux.cfg   

cp -v isolinux.cfg pxelinux.cfg/default

cp -v /usr/share/syslinux/pxelinux.0 /var/lib/tftpboot

```
Finally restart all services and make sure the firewall is off.
``` bash
#system-config-firewall --disable firewall 

service vsftpd restart
service xinetd restart
service dhcpd restart

service vsftpd status

chkconfig vsftpd on
chkconfig xinetd on
chkconfig dhcpd on
```

