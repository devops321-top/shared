# TCPDump Cheat Sheet

### Capture Commands

Use the following commands to capture data packets.

| Command | Example Usage | Explanation |
| ------ | ------ | ------ |
| -i any | tcpdump -i any | Capture from all int. |
| -i eth0 | tcpdump -i eth0 | Capture from int. eth0 |
| -c count | tcpdump -i eth0 -c 5 | Exit after receiving `count (5)` packets |
| -r cap.pcap | tcpdump -i eth0 -r cap.pcap | Read and analyze saved capture file `cap.pcap` |
| tcp | tcpdump -i eth0 tcp | Show TCP packets only |
| udp | tcpdump -i eth0 udp | Show UDP packets only |
| icmp | tcpdump -i eth0 icmp | Show ICMP packets only |
| ip | tcpdump -i eth0 ip | Show IPv4 packets only |
| ip6 | tcpdump -i eth0 ip6 | Show IPv6 packets only |
| arp | tcpdump -i eth0 arp | Show ARP packets only |
| rarp | tcpdump -i eth0 rarp | Show RARP packets only |
| slip | tcpdump -i eth0 slip | Show SLIP packets only |
| <service> | tcpdump http | Filter traffic based on a service |
| <port> | tcpdump port 80 | Filter traffic based on a port number for a service |
| -I | tcpdump -i eth0 -I | Set interface as monitor mode |
| -K | tcpdump -i eth0 -K | Don't verify checksum |
| -p | tcpdump -i eth0 -p | Don't capture in promiscuous mode |
| -n | tcpdump -n -I eth0 | Do not resolve hostname |
| -nn | tcpdump -n -i eth0 | Stop domain name translation and lookups (host names or port names) |
| -S | tcpdump -S http | Display entire packet |

### Filter Commands

Special filter expressions to the tcpdump keyword to pick out specific packets.

| Filter Expression | Explanation |
| ------ | ------ |
| src host 127.0.0.1 | Filter by source IP/hostname `127.0.0.1` |
| dst host 127.0.0.1 | Filter by destination IP/hostname `127.0.0.1` |
| host 127.0.0.1 | Filter by source or destination = `127.0.0.1` |
| ether src 01:23:45:AB:CD:EF | Filter by source MAC `01:23:45:AB:CD:EF` |
| ether dst 01:23:45:AB:CD:EF | Filter by destination MAC `01:23:45:AB:CD:EF` |
| ether host 01:23:45:AB:CD:EF | Filter by source or destination MAC `01:23:45:AB:CD:EF` |
| src net 127.0.0.1 | Filter by source network location `127.0.0.1` |
| dst net 127.0.0.1 | Filter by destination network location `127.0.0.1` |
| net 127.0.0.1 | Filter by source or destination network location `127.0.0.1` |
| net 127.0.0.1/24 | Filter by source or destination network location `127.0.0.1` with the tcpdump subnet mask of lenght `24` |
| src port 80 | Filter by source port = `80` |
| dst port 80 | Filter by destination port = `80` |
| port 80 | Filter by source or destination port = `80` |
| src portrange 80-400 | Filter by source port value between `80` and `400` |
| dst portrange 80-400 | Filter by destination port value between `80` and `400` |
| portrange 80-400 | Filter by source or destination port value between `80` and `400` |
| ether broadcast | Filter for Ethernet broadcasts |
| ip broadcast | Filter for IPv4 broadcasts |
| ether multicast | Filter for Ethernat multicast |
| ip multicast | Filter for IPv4 multicast |
| ip6 multicast | Filter for IPv6 multicast |
| ip src host mydevice | Filter by IPv4 source hostname `mydevice` |
| arp dst host mycar | Filter by ARP destination hostname `mycar` |
| rarp src host 127.0.0.1 | Filter by RARP source `127.0.0.1` |
| ip6 dst host mywatch | Filter by IPv6 destination hostname `mywatch` |
| tcp dst port 8000 | Filter by destination TCP port = `8000` |
| udp src portrange 1000-2000 | Filter by source TCP ports in `1000-2000` |
| sctp port 22 | Filter by source or destination port = `22` |

### Logical Operators

Logical operators indicate how to work with certain traffic.

| Operator | Syntax | Example | Description |
| ------ | ------ | ------ | ------ |
| AND | and, && | tcpdump -n src 192.168.1.1 and dst port 21 | Combine filtering options |
| OR | or, \|\| | tcpdump dst 10.1.1.1 \|\| !icmp | Either of the condition can match |
| EXCEPT | not, ! | tcpdump dst 10.1.1.1 and not icmp | Negation of the comdition |
| LESS | < | tcpdump <32 | Shows packets size less than 32 |
| GREATER | > | tcpdump >=32 | Shows packets size greater than 32 |
| EQUAL | =, == | tcpdump host 127.0.0.1 = 0 | Show packets with zero length |

### Display Commands

These tcpdump switches tell the terminal how to display the outpus.

| Command | Example | Explanation |
| ------ | ------ | ------ |
| -A | tcpdump -i eth0 -A | Print each packet (minus its link level header) in ASCII. Handy for capturing web pages. |
| -D | tcpdump -D | Print the list of the network interfaces available on the system and on which tcpdump can capture packets. |
| -e | tcpdump -i eth0 -e | Print the link-level header on each output line, such as MAC layer addresses for protocols such as Ethernet and IEEE 802.11 |
| -F params.conf | tcpdump -i eth0 -F /path/to/params.conf | Use the file `params.conf` as input for the `filter expression`. (Ignore other expressions on the command line.) |
| -n | tcpdump -i eth0 -n | Don't convert addresses (i.e., host addresses, port numbers, etc.) to names. |
| -u | tcpdump -i eth0 -u | Print undecoded network file system (NFS) handles. |
| -v | tcpdump -i eth0 -v | Produce verbose output. |
| -vv | tcpdump -i eth0 -vv | Additional verbose output than `-v` |
| -vvv | tcpdump -i eth0 -vvv | Additional verbose output than `-vv` |
| -x | tcpdump -i eth0 -x | Print the heades and data of each packet (minus its link level header) in hex. |
| -xx | tcpdump -i eth0 -xx | Print the headers and data of each packet, including its link level header, in hex. |
| -X | tcpdump -i eth0 -X | Print the headers and data of each packet (minus its link level header) in hex and ASCII. |
| -XX | tcpdump -i eth0 -XX | Print the headers and data of each packet, including its link level header, in hex and ASCII. |

### Output Commands

Customize your tcpdump output with the following commands.

| Command | Example | Explanation |
| ------ | ------ | ------ |
| -w captures.pcap | tcpdump -i eth0 -w captures.pcap | Output capture to a file `captures.pcap` |
| -d | tcpdump -i eth0 -d | Display human-readable form in standard output |
| -L | tcpdump -i eth0 -L | Display data link types for the interface |
| -q | tcpdump -i eth0 -q | Quick/quiet output. Print less protocol information, so output lines are shorter |
| -U | tcpdump -i eth0 -U -w out.pcap | `Without -w option` - print a description of each packet's contents. `With -w option` - write each packet to the output file `out.pcap` in real time rather than only when the output buffer fills |
