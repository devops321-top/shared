# Cisco IOS Command

### Cisco IOS Command Hierarchy

There are currently eight modes in Cisco IOS command.
| Prompt | Abbreviation | Description |
| ------ | ------ | ------ |
| `Router>` | U | User EXEC mode, is the first level of access. |
| `Router#` | P | Privileged EXEC mode. The second level of access, accessible with the "enable" command. |
| `Router(config)#` | G | Configuration mode. Accessible only via the privileged EXEC mode. |
| `Router(config-if)#` | I | Interface mode. Level accessible via configuration mode. |
| `Router(config-router)#` | R | Routing mode. Level within configuration mode. |
| `Router(config-line)#` | L | Line level (vty, tty, async). Accessed via the configuration mode. |
| `Router(config-vlan)#` | V | Config-vlan, accessible via the global configuration mode. |
| `Switch(vlan)#` | VD | Vlan database, accessible from the privileged EXEC mode. |

### Basic Configuration Commands

Describes the basic commands for configuring Cisco network devices.
| Command | Mode |  Purpose |
| ------ | ------ | ------ |
| `enable` | U | Logs you into enable mode, which is also know as user exec mode or privileged mode |
| `configure terminal` | P | Logs you into configuration mode |
| `interface <fastethernet/number>` | G | Enters interface configuration mode for the specified fast ethernet interface |
| `reload` | G | An exec mode command that reboots a Cisco switch or router |
| `hostname <name>` | G | Sets a host name to the current Cisco networks device |
| `copy <from-location> <to-location>` | P | An enable mode command that copies files from one file location to another |
| `copy running-config statup-config` | P | An enable mode command that saves the active config, replacing the startup config when a Cisco network device initializes |
| `copy startup-config running-config` | P | An enable mode command that merges the startup config with the currently active config in RAM |
| `write erase` / `erase startup-config` | G | An enable mode command that deletes the startup config |
| `ip address <ip-address> <mask>` | I | Assigns an IP address and subnet mask |
| `shutdown` / `no shutdown` | I | Used in interface configuration mode. "Shutdown" shuts down the interface, while "no shutdown" brings up the interface |
| `ip default-gateway <ip_address>` | G | Sets the default gateway on a Cisco device |
| `show running-config` | P |An enable mode command that displays the current configuration |
| `description <name-string>` | I | A config interface command to descrive or name an interface |
| `show running-config interface <interface slot>/<number>` | P | An enable mode command to display the running configuration for a specific interface |
| `show ip interface <[type number]>` | U, P | Displays the usability status of interfaces that are configured for IP |
| `ip name-server <serverip-1> <serverip-2>` | G | A configure mode command that sets the IP addresses of DNS servers |

### Troubleshooting Commands

Describes the basic commands for troubleshooting Cisco network devices.
| Command | Mode | Purpose |
| ------ | ------ | ------ |
| `ping {hostname\|system-address} [source source-address]` | P | Used in enable mode to diagnose basic network connectivity |
| `speed {10 \| 100 \| 1000 \| auto }` | I | An interface mode command that manually sets the speed to the specified value or negotiates it automatically |
| `duplex {auto \| full \| half}` | I | An interface mode command that manually sets duplex to half, full or auto |
| `cdp run` / `no cdp run` | P |  A configuration mode command that enables or disables Cisco Discovery Protocol (CDP) for the device |
| `show mac address-table` | P |  Displays the MAC address table |
| `show cdp` | P | Shows whether CDP is enabled globally |
| `show cdp neighbors [detail]` | P | Lists summary information about each neighbor connected to this device; the "detail" option lists detailed information about each neighbor |
| `show interfaces` | P | Displays detailed information about interface status, settings and counter |
| `show interface status` | P | Displays the interface line status |
| `show interfaces switchport` | P | Displays a large variety of configuration settings and current operational status, including VLAN trunking details. |
| `show interfaces trunk` | P | Lists information about the currently operational trunks and the VLANs supported by those trunks |
| `show vlan` / `show vlan brief` | P | Lists each VLAN and all interfaces assigned to that VLAN but does not include trunks |
| `show vtp status` | P | Lists the current VTP status, including the current mode |

### Routing and VLAN Commands

Describes the basic commands for routing and vlan Cisco network device.
| Command | Mode | Purpose |
| ------ | ------ | ------ |
| `ip route <network-number> <network-mask> {ip-address \| interface}` | G |  Sets a static route in the IP routing table |
| `router rip` | R | Enables a Routing Information Protocol (RIP) routing process, which places you in router configuration mode |
| `network <ip-address>` | R | In router configuration mode, associates a network with a RIP routing process |
| `version 2` | R | In router configuration mode, configures the software to receive and send only RIPv2 packets |
| `no auto-summary` | R | In router configuration mode, disables automatic summarization |
| `default-information originate` | R | In router configuration mode, generates a default route into RIP |
| `passive-interface <interface>` | R | In router configuration mode, sets only that interface to passive RIP mode. In passive RIP mode, RIP routing updates are accepted by, but not sent out of, the specified interface. |
| `show ip rip database` | P | Displays the contents of the RIP routing database |
| `ip nat [inside \| outside]` | G | An interface configuration mode command to designate that traffic originating from or destined for the interface is subject to NAT |
| `ip nat inside source {list{access-list-number \| access-list-name}} interface type number[overload]`	| G | A configuration mode command to establish dynamic source translation. Use of the “list” keyword enables you to use an ACL to identify the traffic that will be subject to NAT. The “overload” option enables the router to use one global address for many local addresses. |
| `ip nat inside source static <local-ip> <global-ip>` | G | A configuration mode command to establish a static translation between an inside local address and an inside global address | 
| `vlan <1-4094>` | G | Creates a VLAN and enters VLAN configuration mode for further definitions | 
| `switchport access vlan <vlan_number>` | I | Sets the VLAN that the interface belongs to. |
| `switchport trunk encapsulation dot1q` | I | Specifies 802.1Q encapsulation on the trunk link. |
| `switchport access` | I |  Assigns this port to a VLAN |
| `vlan vlan-id [name vlan-name]` | G, V | Configures a specific VLAN name (1 to 32 characters) |
| `switchport mode { access \| trunk }` | I | Configures the VLAN membership mode of a port. The access port is set to access unconditionally and operates as a non-trunking, single VLAN interface that sends and receives non-encapsulated (non-tagged) frames. An access port can be assigned to only one VLAN. The trunk port sends and receives encapsulated (tagged) frames that identify the VLAN of origination. A trunk is a point-to-point link between two switches or between a switch and a router. |
| `switchport trunk {encapsulation { dot1q }` | I | Sets the trunk characteristics when the interface is in trunking mode. In this mode, the switch supports simultaneous tagged and untagged traffic on a port. |
| `encapsulation dot1q vlan-id` | I | A configuration mode command that defines the matching criteria to map 802.1Q frames ingress on an interface to the appropriate service instance. |

### IP Connectivity

This section includes some of the most simple yet useful ip connectivity IOS commands. From displaying a routing table, creating static, to default route and dynamic routes with OSPF.

| Command | Mode | Description |
| ------ | ------ | ------ |
| `show ip route` | P | Show the routing table |
| `show ip route ospf` | P | Show routes created by the OSPF protocol |
| `ip default-gateway <ip_address>` | G | Set the default gateway for the router |
| `ip route <netowrk> <mask> <next hop>` | G | Create a new static route |
| `no ip route <network> <mask> <next hop>` | G | Remove a specific static route |
| `ip route 0.0.0.0 0.0.0.0 <next hop>` | G | Configure a default route |
| `router ospf <process ID>` | G | Enable OSPF with an ID. The command will open the router configuration mode |
| `show ip ospf interface` | P | Display all the active OSPF interfaces |

### DHCP Commands

Describes the basic commands for DHCP Cisco network device.
| Command | Mode | Purpose |
| ------ | ------ | ------ |
| `ip address dhcp` | G | A configuration mode command to acquire an IP address on an interface via DHCP |
| `ip dhcp pool name` | G |  A configuration mode command to configure a DHCP address pool on a DHCP server and enter DHCP pool configuration mode |
| `domain-name <domain>` | G | Used in DHCP pool configuration mode to specify the domain name for a DHCP client | 
| `network <network-number> [mask]` | G | Used in DHCP pool configuration mode to configure the network number and mask for a DHCP address pool primary or secondary subnet on a Cisco IOS DHCP server |
| `ip dhcp excluded-address <ip-address> [last-ip-address]` | G | A configuration mode command to specify IP addresses that a DHCP server should not assign to DHCP clients |
| `ip helper-address <address>` | I | An interface configuration mode command to enable forwarding of UDP broadcasts, including BOOTP, received on an interface |
| `default-router <address[address2 ... address8]>` | G | Used in DHCP pool configuration mode to specify the default router list for a DHCP client |

### Security settings Commands

Describes the basic commands for security settings Cisco network device.
| Command | Mode | Purpose |
| ------ | ------ | ------ |
| `password <pass-value>` | L | Lists the password that is required if the login command (with no other parameters) is conﬁgured |
| `username <name> password <pass-value>` | P | A global command that deﬁnes one of possibly multiple user names and associated passwords used for user authentication. It is used when the login local line conﬁguration command has been used. |
| `enable password <pass-value>` | G | A configuration mode command that deﬁnes the password required when using the enable command |
| `enable secret <pass-value>` | G | A configuration mode command that sets this Cisco device password that is required for any user to enter enable mode |
| `service password-encryption` | G | A configuration mode command that directs the Cisco IOS software to encrypt the passwords, CHAP secrets, and similar data saved in its configuration file |
| `ip domain-name <name>` | G |  Conﬁgures a DNS domain name |
| `crypto key generate rsa` | G | A configuration mode command that creates and stores (in a hidden location in ﬂash memory) the keys that are required by SSH |
| `transport input {telnet \| ssh}` | G | Used in vty line conﬁguration mode, deﬁnes whether Telnet or SSH access is allowed into this switch. Both values can be specified in a single command to allow both Telnet and SSH access (default settings). |
| `access-list <access-list-number> {deny \| permit} source [source-wildcard] [log]` | G | A configuration mode command that defines a standard IP access list |
| `access-class` | L | Restricts incoming and outgoing connections between a particular vty (into a basic Cisco device) and the addresses in an access list |
| `ip access-list {standard \| extended} {access-list-name \| access-list-number}` | G | A configuration mode command that defines an IP access list by name or number |
| `permit source [source-wildcard]` | G | Used in ACL configuration mode to set conditions to allow a packet to pass a named IP ACL. To remove a permit condition from an ACL, use the “no” form of this command. |
| `deny source [source-wildcard]` | G | Used in ACL configuration mode to set conditions in a named IP ACL that will deny packets. To remove a deny condition from an ACL, use the “no” form of this command. |
| `ntp peer <ip-address>` | G | Used in global configuration mode to configure the software clock to synchronize a peer or to be synchronized by a peer |
| `switchport port-security` | I | Used in interface configuration mode to enable port security on the interface |
| `switchport port-security maximum maximum` | I | Used in interface configuration mode to set the maximum number of secure MAC addresses on the port |
| `switchport port-security mac-address {mac-addr \| {sticky [mac-addr]}}` | I | Used in interface configuration mode to add a MAC address to the list of secure MAC addresses. The “sticky” option configures the MAC addresses as sticky on the interface. |
| `switchport port-security violation {shutdown \| restrict \| protect}` | I | Used in interface configuration mode to set the action to be taken when a security violation is detected |
| `show port security [interface interface-id]` | P | Displays information about security options configured on the interface |

### Monitoring and Logging Commands

Describes the basic commands for monitoring and logging Cisco network device.
| Command | Mode | Purpose |
| ------ | ------ | ------ |
| `logging <ip address>` | G | Configures the IP address of the host that will receive the system logging (syslog) messages |
| `logging trap level` | G | Used in configuration mode to limit messages that are logged to the syslog servers based on severity. Specify the number or name of the desired severity level at which messages should be logged. |
| `show logging` | P | Enable mode command that displays the state of system logging (syslog) and the contents of the standard system logging buffer. |
| `terminal monitor` | P | An enable mode command that tells Cisco IOS to send a copy of all syslog messages, including debug messages, to the Telnet or SSH user who issues this command |
