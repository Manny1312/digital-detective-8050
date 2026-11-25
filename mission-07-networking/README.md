# Mission 7 — Networking Investigation

## Task
Test local and external network connectivity, trace how domain names translate into IP addresses via DNS, inspect HTTP response headers, and summarize key networking protocols.

## Work Completed

### Loopback & External Connectivity (`ping`)
Tested my MacBook's internal network stack using the loopback address (`127.0.0.1`) and verified internet reachability and round-trip latency to `github.com`:

```text
\$ ping -c 3 127.0.0.1
PING 127.0.0.1 (127.0.0.1): 56 data bytes
64 bytes from 127.0.0.1: icmp_seq=0 ttl=64 time=0.068 ms
64 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.112 ms
64 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.095 ms
--- 127.0.0.1 ping statistics ---
3 packets transmitted, 3 packets received, 0.0% packet loss

\$ ping -c 3 github.com
PING github.com (20.207.73.82): 56 data bytes
64 bytes from 20.207.73.82: icmp_seq=0 ttl=115 time=38.4 ms
64 bytes from 20.207.73.82: icmp_seq=1 ttl=115 time=37.9 ms
64 bytes from 20.207.73.82: icmp_seq=2 ttl=115 time=39.1 ms
--- github.com ping statistics ---
3 packets transmitted, 3 packets received, 0.0% packet loss
```

### DNS Name Resolution (`nslookup`)
Checked how the Domain Name System (DNS) translates the human-readable domain `github.com` into a routable IPv4 address:

```text
\$ nslookup github.com
Server:		192.168.1.1
Address:	192.168.1.1#53

Non-authoritative answer:
Name:	github.com
Address: 20.207.73.82
```

### HTTP/HTTPS Header Inspection (`curl -I`)
Sent a HEAD request to `https://github.com` to inspect the server's HTTP protocol version and status code without downloading the full webpage:

```text
\$ curl -I -s https://github.com | head -n 5
HTTP/2 200
date: Wed, 25 Nov 2026 11:58:10 GMT
content-type: text/html; charset=utf-8
server: GitHub.com
```

### Key Networking Concepts & Protocols

| Protocol / Term | Purpose | Example from Investigation |
| :--- | :--- | :--- |
| **IP Address** | Unique numerical label identifying a device or server on a network. | `127.0.0.1` (localhost) and `20.207.73.82` (GitHub) |
| **DNS (Port 53)** | Translates human-friendly domain names into IP addresses. | `nslookup github.com` resolving to an IPv4 address |
| **ICMP (`ping`)** | Tests whether a host is reachable and measures round-trip latency in milliseconds. | `ping -c 3 github.com` showing ~38 ms response time |
| **HTTPS (Port 443)** | Encrypts web traffic between my browser/CLI and remote servers using TLS. | `curl -I https://github.com` returning `HTTP/2 200` |

## Commands / Tools Used
* **macOS Terminal / Zsh** inside Visual Studio Code.
* **Networking CLI Tools**: `ping -c 3`, `nslookup`, `curl -I`.
* **Git** (`git add`, `git commit`, `git push`) to save and upload Mission 7 separately.

## My Understanding
Every time I run `git push` or load a webpage, multiple networking layers work together: DNS resolves the domain name into an IP address, TCP/IP routes packets across the internet, and HTTPS encrypts the data in transit. Testing `127.0.0.1` separately from an external domain helps isolate whether a network issue is on my own device or outside on the internet.

## Difficulties Faced
Running plain `ping github.com` on macOS kept sending packets infinitely until stopped manually, and `ifconfig` output included local hardware/MAC addresses that shouldn't be shared publicly.

## How I Resolved Them
Added the `-c 3` flag to `ping` so it stops automatically after three packets, and focused the documented outputs on loopback (`127.0.0.1`) and public server responses (`github.com`) to keep personal network identifiers private.

## Evidence / Files
* `mission-07-networking/README.md`

## Commit Details
* **Commit Message**: `Complete networking investigation mission`