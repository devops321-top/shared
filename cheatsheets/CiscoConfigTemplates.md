### Initial Configuration (switches and routers)

This section includes initial configuration Cisco switches and routers.

| Command | Mode | What It Does |
| ------ | ------ | ------ |
| `hostname <xyz>` | G | Sets hostname to xyz |
| `enable secret <xyz>` | G | Sets encrypted password for priv. EXEC to xyz |
| `service password-encrypt` | G | Encrypts all passwords |
| `line console 0` | G | Enters line config mode for console |
| `line vty 0 15` | G | Enters line config mode for 16 vty lines |
| `password <xyz>` | L | Sets line password to xyz |
| `login` | L | Enables users to login |
| `int vlan 1` | G | Enters interface config mode for vlan1 |
| `ip address <ip> <subnet>` | I | Sets IP address |
| `no shut` | I | Turns on interface |
| `banner motd #Text Here# | G | Sets MOTD banner |

### Router-specific configuration commands

This section includes router-specific configuration Cisco routers.

| Command | Mode | What It Does |
| ------ | ------ | ------ |
| `interface g0/1` | G | Enters interface config for Gigabit Ethernet 0/1 |
| `ip address IP/prefix` | I | Sets interface's IPv4 address |
| `no shut` | I | Turns on the interface |
| `description <description text>` | I | Used to document info about the interface |
| `ipv6 address IP/prefix` | I | Sets interface's IPv6 address |
| `ipv6 address IP/prefix link-local` | I | Sets interface's IPv6 link-local address |
| `ipv6 unicast-routing | G | Enables IPv6 routing |

