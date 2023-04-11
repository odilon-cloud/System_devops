# To create sub-interface

go to the network-script file

``` bash
 cd /etc/sysconfig/network-scripts/

```
and copy the existing interface

``` bash
 cp ifcfg-eth0 ifcfg-eth0:1
 vim ifcfg-eth0:1
```
rename the device , ip_address and subnet mask
## Create a link from the new device definition 
you created in each case of the networking Configuration directrories where the network  management scripts expect to find them

``` bash
ln ifcfg-eth0:1 ../networking/device/
ln ifcfg-eth0:1 ../networking/profiles/default/
```
restart all 
	1. network 
	2. network manager
	3. the interface
the same with ipv6
