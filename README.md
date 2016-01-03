## Lightweight DD-WRT Blocklist

This is a **small** list of advertising and analytic domains for blocking in DD-WRT routers. The list is in DNSMasq format.

The intention of this list is to block the more common ad and analytics servers, without overwhelming comsumer routers with lists containing 5000+ domains.

### Installation

Copy the contents of **list.txt** into 'Additional DNSMasq Options' under 'Services>Services>DNSMasq' in the DD-WRT control Panel.

Make sure DNSMasq is enabled, and client devices are getting **only** the router's IP address via DHCP for DNS.
