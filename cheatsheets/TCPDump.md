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
