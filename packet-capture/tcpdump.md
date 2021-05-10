# TCPDUMP
`tcpdump` is a command line tool for capturing packets from a network. It is available for Linux, Windows, and MacOS.

On Linux, it may already be installed.

## Common Uses

List all the network interfaces on the current machine that available for listening.
```
   $ tcpdump -D
```
Start a capture from a wireless card. The capture will continue until you use CTRL+C to end it.
```
   $ tcpdump -i wls1
```
Capture 10 packets using the Count flag.
```
   $ tcpdump -i wls1 -c 10
```
 Reduce the amount of data captured by turning off name resolution - it keeps your device from making DNS requests.
 ```
    $ tcpdump -i wls1 -c10 -nn
 ```
 
