# VLAN Tagging using a Cisco Layer 3 Switch

For this project we will be tagging the two VLANs configured inside both Ubuntu 18.04 Servers.

Our topology looks like this:

[![Usntitled.png](https://i.postimg.cc/3xNTKb5n/Usntitled.png)](https://postimg.cc/GHWNKKpy)

Here we will be sending tagged VLAN frames which will be done between two IPs in two servers.

VLAN10: 192.168.10.2 192.168.10.3
VLAN20: 192.168.20.2 192.168.20.3

We won't be doing VLAN routing so communications will only be between the IPs inside the same VLAN.

First start the switch.

```
***************************************************************
This is a normal Router with a SW module inside (NM-16ESW)
It has been preconfigured with hard coded speed and duplex

To create vlans use the command "vlan database" from exec mode
After creating all desired vlans use "exit" to apply the config

To view existing vlans use the command "show vlan-switch brief"

Warning: You are using an old IOS image for this router.
Please update the IOS to enable the "macro" command!
***************************************************************


ESW1#

```
then do the configs below.

`
vlan database
`

```
vlan 10

vlan 20
```

`
exit
`

Now that you have created the VLANs you can see them using 

`
show vlan-switch
`

Then proceed to the interfaces and make them trunk.

`
conf t 
`

```
int fa 0/0

	switchport mode trunk
  
	no shutdown
  
exit
```

```
int fa 0/1

	switchport mode trunk
  
	no shutdown(no sh)
```

`end
`

You are done with the switch. You can see the trunked interfaces using

`
show interface switchport
`







