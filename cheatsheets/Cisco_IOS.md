# Cisco IOS Command

### Basic Configuration Commands

Describes the basic commands for configuring Cisco network devices.
| Command | Purpose |
| ------ | ------ |
| enable | Logs you into enable mode, which is also know as user exec mode or privileged mode |
| configure terminal | Logs you into configuration mode |
| interface fastethernet/number | Enters interface configuration mode for the specified fast ethernet interface |
| reload | An exec mode command that reboots a Cisco switch or router |
| hostname name | Sets a host name to the current Cisco networks device |
| copy from-location to-location | An enable mode command that copies files from one file location to another |
| copy running-config statup-config | An enable mode command that saves the active config, replacing the startup config when a Cisco network device initializes |
| copy startup-config running-config | An enable mode command that merges the startup config with the currently active config in RAM |
| write erase / erase startup-config | An enable mode command that deletes the startup config |
| ip address ip-address mask | Assigns an IP address and subnet mask |
| shutdown / no shutdown | Used in interface configuration mode. "Shutdown" shuts down the interface, while "no shutdown" brings up the interface |
| ip default-gateway ip_address | Sets the default gateway on a Cisco device |
| show running-config | An enable mode command that displays the current configuration |
| description name-string | A config interface command to descrive or name an interface |
| show running-config interface interface slot/number | An enable mode command to display the running configuration for a specific interface |
| show ip interface [type number] | Displays the usability status of interfaces that are configured for IP |
| ip name-server serverip-1 serverip-2 | A configure mode command that sets the IP addresses of DNS servers |

### Troubleshooting Commands

Describes the basic commands for troubleshooting Cisco network devices.
| Command | Purpose |
| ------ | ------ |
| ping {hostname\|system-address} [source source-address] | Used in enable mode to diagnose basic network connectivity |
| speed {10 \| 100 \| 1000 \| auto } | An interface mode command that manually sets the speed to the specified value or negotiates it automatically |
| duplex {auto \| full \| half} | An interface mode command that manually sets duplex to half, full or auto |
| cdp run / no cdp run | A configuration mode command that enables or disables Cisco Discovery Protocol (CDP) for the device |
| show mac address-table | Displays the MAC address table |
| show cdp | Shows whether CDP is enabled globally |
| show cdp neighbors[detail] | Lists summary information about each neighbor connected to this device; the "detail" option lists detailed information about each neighbor |
| show interfaces | Displays detailed information about interface status, settings and counter |
| show interface status | Displays the interface line status |
| show interfaces switchport | Displays a large variety of configuration settings and current operational status, including VLAN trunking details. |
| show interfaces trunk | Lists information about the currently operational trunks and the VLANs supported by those trunks |
| show vlan / show vlan brief | Lists each VLAN and all interfaces assigned to that VLAN but does not include trunks |
| show vtp status | Lists the current VTP status, including the current mode |

### Routing and VLAN Commands

Describes the basic commands for routing and vlan Cisco network device.
| Command | Purpose |
| ------ | ------ |
| ip route network-number network-mask {ip-address \| interface} | Sets a static route in the IP routing table |
| router rip | Enables a Routing Information Protocol (RIP) routing process, which places you in router configuration mode |
| network ip-address | In router configuration mode, associates a network with a RIP routing process |
| version 2 | In router configuration mode, configures the software to receive and send only RIPv2 packets |
| no auto-summary | In router configuration mode, disables automatic summarization |
| default-information originate	| In router configuration mode, generates a default route into RIP |
| passive-interface interface | In router configuration mode, sets only that interface to passive RIP mode. In passive RIP mode, RIP routing updates are accepted by, but not sent out of, the specified interface. |
| show ip rip database | Displays the contents of the RIP routing database |
| ip nat [inside \| outside] | An interface configuration mode command to designate that traffic originating from or destined for the interface is subject to NAT |
| ip nat inside source {list{access-list-number \| access-list-name}} interface type number[overload]	| A configuration mode command to establish dynamic source translation. Use of the “list” keyword enables you to use an ACL to identify the traffic that will be subject to NAT. The “overload” option enables the router to use one global address for many local addresses. |
| ip nat inside source static local-ip global-ip | A configuration mode command to establish a static translation between an inside local address and an inside global address | 
| vlan | Creates a VLAN and enters VLAN configuration mode for further definitions | 
| switchport access vlan | Sets the VLAN that the interface belongs to. |
| switchport trunk encapsulation dot1q | Specifies 802.1Q encapsulation on the trunk link. |
| switchport access	| Assigns this port to a VLAN |
| vlan vlan-id [name vlan-name]	| Configures a specific VLAN name (1 to 32 characters) |
| switchport mode { access \| trunk } | Configures the VLAN membership mode of a port. The access port is set to access unconditionally and operates as a non-trunking, single VLAN interface that sends and receives non-encapsulated (non-tagged) frames. An access port can be assigned to only one VLAN. The trunk port sends and receives encapsulated (tagged) frames that identify the VLAN of origination. A trunk is a point-to-point link between two switches or between a switch and a router. |
| switchport trunk {encapsulation { dot1q }	| Sets the trunk characteristics when the interface is in trunking mode. In this mode, the switch supports simultaneous tagged and untagged traffic on a port. |
| encapsulation dot1q vlan-id | A configuration mode command that defines the matching criteria to map 802.1Q frames ingress on an interface to the appropriate service instance. |

### DHCP Commands

Describes the basic commands for DHCP Cisco network device.
| Command | Purpose |
| ------ | ------ |
| ip address dhcp | A configuration mode command to acquire an IP address on an interface via DHCP |
| ip dhcp pool name	| A configuration mode command to configure a DHCP address pool on a DHCP server and enter DHCP pool configuration mode |
| domain-name domain | Used in DHCP pool configuration mode to specify the domain name for a DHCP client | 
| network network-number [mask]	| Used in DHCP pool configuration mode to configure the network number and mask for a DHCP address pool primary or secondary subnet on a Cisco IOS DHCP server |
| ip dhcp excluded-address ip-address [last-ip-address]	| A configuration mode command to specify IP addresses that a DHCP server should not assign to DHCP clients |
| ip helper-address address	| An interface configuration mode command to enable forwarding of UDP broadcasts, including BOOTP, received on an interface |
| default-router address[address2 ... address8]	| Used in DHCP pool configuration mode to specify the default router list for a DHCP client |

