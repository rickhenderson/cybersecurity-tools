# TCPDUMP
`tcpdump` is a command line tool for capturing packets from a network. It is available for Linux, Windows, and MacOS.

On Linux, it may already be installed.

## Common Uses

List all the network interfaces on the current machine that available for listening.
```
   $ sudo tcpdump -D
```
Start a capture from a wireless card. The capture will continue until you use CTRL+C to end it.
```
   $ sudo tcpdump -i wls1
```
Capture 10 packets using the Count flag.
```
   $ sudo tcpdump -i wls1 -c 10
```
 Reduce the amount of data captured by turning off name resolution - it keeps your device from making DNS requests.
 ```
    $ sudo tcpdump -i wls1 -c10 -nn
 ```
 
 ## Filtering
 ``` 
    $ sudo tcpdump -i any -c100 -n ICMP 
 ```
 
 Output captured packets in ASCII, useful for debugging web requests.
 ``` 
    $ sudo tcpdump -c100 -n -A port 80 
 ```
 
 Write captured packets to a ```pcap``` file. These files can be read by Wireshark and examined later.
 ``` 
    $ sudo tcpdump -w webtraffic.pcap port 80 
 ``` 
 
## NOTES
Check the `man` pages.
To  print  all  IPv4 HTTP packets to and from port 80, i.e. print only packets that contain data, not, for example, SYN and FIN packets and ACK-only packets.  (IPv6 is left as an exercise for the reader.)
```
   $ tcpdump 'tcp port 80 and (((ip[2:2] - ((ip[0]&0xf)<<2)) - ((tcp[12]&0xf0)>>2)) != 0)'
```
Some information in this tutorial was taken from <a href="https://opensource.com/article/18/10/introduction-tcpdump">An Introduction to using tcpdump at the Linux command line</a>.
