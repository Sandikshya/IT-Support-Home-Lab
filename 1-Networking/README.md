## Networking Fundamentals

Basic Networking:

1. Find your Mac's IP address
   Open Terminal on your Mac and enter " ifconfig getifaddr en0"
   
2. Find your default gateway:
   Enter " route -n get default"

Now this section documents practical networking troubleshooting exercises completed as part of my IT Support Home Lab.

#### 1. Testing Network Connectivity with Ping
What I learned
ping is a basic network troubleshooting tool used to test whether a device can reach another IP address across a network.
I used Google's public DNS server (8.8.8.8) as the destination.
*** Command used ***
ping -c 4 8.8.8.8
The -c 4 option tells macOS to send 4 ICMP echo requests and then stop.
##### Result
* 4 packets transmitted
* 4 packets received
* 0.0% packet loss
* Average round-trip time: approximately 24 ms
What this showed
The test confirmed that my Mac could successfully communicate with 8.8.8.8 and that no packets were lost during the test.

#### 2. Testing a Domain Name with Ping
What I learned
When I ping a domain name instead of an IP address, the computer first needs to resolve the domain name to an IP address using DNS.
Command used
ping -c 4 google.com
The test resolved google.com to an IPv4 address and then successfully sent and received the packets.
Result
* 4 packets transmitted
* 4 packets received
* 0.0% packet loss
* Average round-trip time: approximately 24 ms
What this showed
The test confirmed both:
1. DNS was able to resolve google.com to an IP address.
2. My Mac could communicate with the resolved IP address.

#### 3. DNS Troubleshooting with nslookup
What I learned
DNS (Domain Name System) translates human-readable domain names into IP addresses.
For example:
google.com → IP address
nslookup can be used to check DNS resolution and identify which DNS server is responding.
Command used
nslookup google.com
#### Result
The command showed that my Mac was using a local DNS server and successfully received an IPv4 address for google.com.
What this showed
DNS resolution was working correctly on my network.
The DNS service uses port 53.

### Troubleshooting Approach
These tests demonstrated a basic troubleshooting process:
Test 1 — Can I reach an IP address?
ping -c 4 8.8.8.8
Test 2 — Can I resolve and reach a domain name?
ping -c 4 google.com
Test 3 — Is DNS resolution working?
nslookup google.com
Using these tests helps distinguish between a general connectivity problem and a DNS-related problem.

### Key Concepts Learned
* IP address
* Network connectivity
* ICMP
* Ping
* Packet loss
* Latency / round-trip time
* DNS
* DNS server
* Domain name resolution
* Port 53
* Basic network troubleshooting
