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
| 'or' or `||` | Logical OR | Either all or one of the conditions should match |
| xor or ^^ | Logical XOR | Exclusive alterations - only one of the two conditions should match not both |
| not or ! | Not (Negation) | Not equal to |
| [ n ]  [ ... ] | Substring operator | Filter a specific word or text |
