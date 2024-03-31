- Lists available Wi-Fi access points known to NetworkManager:
> `$ nmcli dev wifi`

---

- Show all network interfaces
> `$ lshw -class network`

---

- Show the parameters and statistics of all the interfaces:
> `$ iwconfig`

- Show the parameters and statistics of the specified interface:
> `$ iwconfig {{interface}}`

- Set the ESSID (network name) of the specified interface (e.g. eth0 or wlp2s0):
> `$ iwconfig {{interface}} {{new_network_name}}`

- Set the operating mode of the specified interface:
> `$ iwconfig {{interface}} mode {{ad hoc|Managed|Master|Repeater|Secondary|Monitor|Auto}}`

---

- Ping host:
> `$ ping {{host}}`

- Ping a host only a specific number of times:
> `$ ping -c {{count}} {{host}}`

- Ping host, specifying the interval in seconds between requests (default is 1 second):
> `$ ping -i {{seconds}} {{host}}`

---

- Follow new messages for NetworkManager Unit
> `$ journalctl -f -u NetworkManager`

- Show all messages for NetworkManager Unit
> `$ journalctl -u NetworkManager`

- Filter messages within a time range (either timestamp or placeholders like "yesterday"):
> `$ journalctl --since {{now|today|yesterday|tomorrow}} --until {{YYYY-MM-DD HH:MM:SS}}`

Show all messages by a specific process:
> `$ journalctl _PID={{pid}}`

- Show all messages by a specific executable:
> `$ journalctl {{path/to/executable}}`

---

- List listening TCP and UDP ports (+ user and process if you're root):
> `$ apt install net-tools`

> `$ netstat --listening --program --numeric --tcp --udp --extend`

---

- Display the information of route table:
> `$ route -n`

---

- Show the current ARP table:
> `$ arp -a`

---

- Display details of all interfaces, including disabled interfaces:
> `$ ifconfig -a`

- View network settings of an Ethernet adapter:
> `$ ifconfig {{eth0}}`

- Disable eth0 interface:
> `$ ifconfig {{eth0}} down`

- Enable eth0 interface:
> `$ ifconfig {{eth0}} up`

---

> `$ lft {{google.com}}`

---

- Enable ufw:
> `$ ufw enable`

- Disable ufw:
> `$ ufw disable`

- Show ufw rules, along with their numbers:
> `$ ufw status numbered`

- Allow incoming traffic on port 5432 on this host with a comment identifying the service:
> `$ ufw allow {{5432}} comment "{{Service}}"`

- Allow only TCP traffic from 192.168.0.4 to any address on this host, on port 22:
> `$ ufw allow proto {{tcp}} from {{192.168.0.4}} to {{any}} port {{22}}`

- Deny traffic on port 80 on this host:
> `$ ufw deny {{80}}`

- Deny all UDP traffic to port 22:
> `$ ufw deny proto {{udp}} from {{any}} to {{any}} port {{22}}`

- Delete a particular rule. The rule number can be retrieved from the ufw status numbered command:
> `$ ufw delete {{rule_number}}`

---

- View chains, rules, and packet/byte counters for the filter table:
> `$ sudo iptables -vnL`

- Set chain policy rule:
> `$ sudo iptables -P {{chain}} {{rule}}`

- Append rule to chain policy for IP:
> `$ sudo iptables -A {{chain}} -s {{ip}} -j {{rule}}`

- Append rule to chain policy for IP considering protocol and port:
> `$ sudo iptables -A {{chain}} -s {{ip}} -p {{protocol}} --dport {{port}} -j {{rule}}`

- Add a NAT rule to translate all traffic from the 192.168.0.0/24 subnet to the host's public IP:
> `$ sudo iptables -t {{nat}} -A {{POSTROUTING}} -s {{192.168.0.0/24}} -j {{MASQUERADE}}`

- Delete chain rule:
> `$ sudo iptables -D {{chain}} {{rule_line_number}}`

- Save iptables configuration of a given table to a file:
> `$ sudo iptables-save -t {{tablename}} > {{path/to/iptables_file}}`

- Restore iptables configuration from a file:
> `$ sudo iptables-restore < {{path/to/iptables_file}}`

---

- Query your system's default name server for an IP address (A record) of the domain:
> `$ nslookup {{example.com}}`

- Query a given name server for a NS record of the domain:
> `$ nslookup -type=NS {{example.com}} {{8.8.8.8}}`

- Query for a reverse lookup (PTR record) of an IP address:
> `$ nslookup -type=PTR {{54.240.162.118}}`

- Query for ANY available records using TCP protocol:
> `$ nslookup -vc -type=ANY {{example.com}}`

- Query a given name server for the whole zone file (zone transfer) of the domain using TCP protocol:
> `$ nslookup -vc -type=AXFR {{example.com}} {{name_server}}`

- Query for a mail server (MX record) of the domain, showing details of the transaction:
> `$ nslookup -type=MX -debug {{example.com}}`

- Query a given name server on a specific port number for a TXT record of the domain:
> `$ nslookup -port={{port_number}} -type=TXT {{example.com}} {{name_server}}`

---
