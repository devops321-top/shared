# Wireshark Cheat Sheet

### Default columns in a packet capture output
| Columns | Description |
| ------ | ------ |
| No. | Frame number from the begining of the capture |
| Time | Seconds from the first frame |
| Source (src) | Source address, commonly an IPv4, IPv6 or Ethernet address |
| Destination (dst) | Destination adress |
| Protocol | Protocol used in the Ethernet frame, IP packet, or TC segment |
| Lenght | Length of the frame in bytes |

### Logical operators
| Operator | Description | Example |
| ------| ------ | ------ |
| and or && | Logical AND | All the conditions should match |
| 'or' or \|\| | Logical OR | Either all or one of the conditions should match |
| xor or ^^ | Logical XOR | Exclusive alterations - only one of the two conditions should match not both |
| not or ! | Not (Negation) | Not equal to |
| [ n ]  [ ... ] | Substring operator | Filter a specific word or text |

### Filtering packets (Display Filters)
| Operator | Description | Example |
| ------ | ------ | ------ |
| eq or == | Equal | ip.dest == 192.168.1.1 |
| ne or != | Not equal | ip.dest != 192.168.1.1 |
| gt or > | Greater than | frame.len > 10 |
| it or < | Less than | frame.len < 10 |
| ge or >= | Greater than or equal | frame.len >= 10 |
| le or <= | Less than or equal | frame.len <= 10 |

### Filter types
| Name is filter | Description |
| ------ | ------ |
| Capture filter | Filter packets during capture |
| Display filter | Hide packets from a capture display |

### Capture Filter Syntax
| Syntax | Protocol | Direction | Hosts | Value | Logical operator | Expressions |
| ------ | ------ | ------ |  ------ | ------ | ------ | ------ |
| Example | tcp | src | 192.168.1.1 | 80 | and | tcp dst 202.164.30.1 |

### Display Filter Syntax
| Syntax | Protocol | String 1 | String 2 | Comparison Operator | Value | Logical Operator | Expressions |
| ------ | ------ | ------ |  ------ | ------ | ------ | ------ | ------ |
|Example | http | dest | ip | == | 192.168.1.1 | and | tcp port |

### Common Filtering commands
| Usage | Filter syntax |
| ------ | ------ |
| Filter by IP | ip.add == 10.10.50.1 |
| Filter by Destination IP | ip.dest == 10.10.50.1 |
| Filter by Source IP | ip.src == 10.10.50.1 |
| Filter by IP range | ip.addr >= 10.10.50.1 and ip.addr <= 10.10.50.100 |
| Filter by multiple IPs | ip.addr == 10.10.50.1 and ip.addr == 10.10.50.100 |
| Filter out IP address | !(ip.addr == 10.10.50.1) |
| Filter subnet | ip.addr == 10.10.50.1/24 |
| Filter by port | tcp.port == 25 |
| Filter by destination port | tcp.dstport == 23 |
Filter by IP address and port | ip.addr == 10.10.50.1 and tcp.port == 25 |
| Filter by URL | http.host == "hostname" |
| Filter by time stamp | frame.time >= "June 02, 2019 18:04:00" |
| Filter SYN flag | `tcp.flags.syn == 1` or `tcp.flags.syn == 1 and tcp.flag.ack == 0` |
| Wireshark Beacon Filter | wlan.fc.type_subtype = 0x08 |
| Wireshark Broadcast filter | eth.dst == ff:ff:ff:ff:ff:ff |
| Wireshark multicast filter | (eth.dst[0] & 1) |
| Host name filter | ip.host = hostname |
| MAC address filter | eth.addr == 00:70:f4:23:18:c4 |
| RST flag filter | tcp.flag.reset == 1 |
| List the HTTP GET requests | http.request |
