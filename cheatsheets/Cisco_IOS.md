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

