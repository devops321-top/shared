# TCPDump Cheat Sheet

### Capture Commands
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
| -I | tcpdump -i eth0 -I | Set interface as monitor mode |
| -K | tcpdump -i eth0 -K | Don't verify checksum |
| -p | tcpdump -i eth0 -p | Don't capture in promiscuous mode|

### Filter Commands

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

| Operator | Syntax | Example | Description |
| ------ | ------ | ------ | ------ |
| AND | and, && | tcpdump -n src 192.168.1.1 and dst port 21 | Combine filtering options |
| OR | or, \|\| | tcpdump dst 10.1.1.1 \|\| !icmp | Either of the condition can match |
| EXCEPT | not, ! | tcpdump dst 10.1.1.1 and not icmp | Negation of the comdition |
| LESS | < | tcpdump <32 | Shows packets size less than 32 |
| GREATER | > | tcpdump >=32 | Shows packets size greater than 32 |

