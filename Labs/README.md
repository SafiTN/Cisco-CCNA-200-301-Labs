 
This lab explores DNS client configuration on Cisco routers and the ARP cache.
Configure the Routers as DNS Clients
Note that routers cannot be DNS servers in Packet Tracer (it does not
support the ‘ip dns server’ command) so we are using a Packet Tracer
server device as the DNS server.
The host with IP address 10.10.10.10 has been configured as a DNS server and
is able to resolve DNS requests for ‘R1’, ‘R2’ and ‘R3’.
A domain name is not in use.
1) Configure R1, R2 and R3 to use 10.10.10.10 as their DNS server. You do
not need to configure a domain-name or domain-list.
R1(config)#ip domain-lookup
R1(config)#ip name-server 10.10.10.10
R2(config)#ip domain-lookup
R2(config)#ip name-server 10.10.10.10
R3(config)#ip domain-lookup
R3(config)#ip name-server 10.10.10.10
2) Verify that you can ping R2 and R3 from R1 using their hostnames ‘R2’
and ‘R3’ (it may take some time for the DNS server to resolve the DNS
request).
R1#ping R2
Translating "R2"...domain server (10.10.10.10)
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.10.10.2, timeout is 2
seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max =
0/0/1 ms
R1#ping R3
Translating "R3"...domain server (10.10.10.10)
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.10.20.1, timeout is 2
seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max =
0/0/1 ms
3) Verify that you can ping R1 and R2 from R3 using their hostnames ‘R1’
and ‘R2’.
R3#ping R1
Translating "R1"...domain server (10.10.10.10)
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.10.10.1, timeout is 2
seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max =
0/0/2 ms
R3#ping R2
Translating "R2"...domain server (10.10.10.10)
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.10.10.2, timeout is 2
seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max =
0/0/2 ms