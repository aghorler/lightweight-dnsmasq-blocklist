## Lightweight DNSMasq Blocklist

This is an **intentionally small** list of advertising and analytic domains for blocking in custom router firmware - such as DD-WRT, LEDE, and Tomato. The list is in dnsmasq configuration format.

The intention of this list is to block common advertising and analytics domains without overwhelming consumer routers with lists containing 5000+ ultra-specific domains.

### Installation

**dnsmasq (General Linux)**

Copy the contents of **[list.txt](https://raw.githubusercontent.com/aghorler/lightweight-dnsmasq-blocklist/master/list.txt)** into `/etc/dnsmasq.conf`.

**LEDE**

Create `/etc/dnsmasq.conf`, and copy the contents of **[list.txt](https://raw.githubusercontent.com/aghorler/lightweight-dnsmasq-blocklist/master/list.txt)** into the file.

Or use wget.

`wget https://raw.githubusercontent.com/aghorler/lightweight-dnsmasq-blocklist/master/list.txt -O /etc/dnsmasq.conf`

Ensure dnsmasq is enabled, and client devices are using **only** the IP address of the router for DNS.

A firewall rule (`Network > Firewal` in the GUI) can be used to force the router be used for DNS.

`iptables -t nat -A PREROUTING -i br-lan -p udp --dport 53 -j DNAT --to 192.168.1.1`

`iptables -t nat -A PREROUTING -i br-lan -p tcp --dport 53 -j DNAT --to 192.168.1.1`

**DD-WRT**

Copy the contents of **[list.txt](https://raw.githubusercontent.com/aghorler/lightweight-dnsmasq-blocklist/master/list.txt)** into `Additional DNSMasq Options` under `Services > Services > DNSMasq` in the DD-WRT Control Panel. Instructions vary for other firmware.

Ensure dnsmasq is enabled, and client devices are using **only** the IP address of the router for DNS.

---

#### Privacy

This list is solely a text file, and is not capable of collecting user data. 

All blocked domains are redirected to the invalid IP address `0.0.0.0`.

#### License

Copyright 2018 Aaron Horler

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
