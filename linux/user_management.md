- To Know The Current Shell User:
> `$ sudo whoami`

- Connect To Root:
> `$ sudo -i or su`

- Change Root Password:
> `$ sudo passwd`

- Connect To ==username==:
> `$ su <username>`

- Add ==username==:
> `$ sudo adduser <username>`

- See all groups of ==username==:
> `$ grep <username> /etc/group or groups <username>`

- See all groups:
> `$ sudo cat /etc/group`

- See all users:
> `$ sudo cat /etc/passwd`

- See members of ==groupname==:
> `$ getent group <groupname>`

- Add ==groupname== Group:
> `$ sudo groupadd <groupname>`

- Delete A Group ==groupname==:
> `$ sudo groupdel <groupname>`

- Add ==username== to ==groupname==:
> `$ sudo gpasswd -a <username> <groupname>`

or

> `$ sudo adduser <username> <groupname>`

- Delete ==username== from ==groupname==:
> `$ sudo gpasswd -d <username> <groupname>`

---

Switch primary group membership

- Change user's primary group membership:
> `$ newgrp {{group_name}}`

- Reset primary group membership to user's default group in /etc/passwd:
> `$ newgrp`

Example:
> `$ newgrp docker`

---

Get or set the hostname of the computer

- Get the hostname of the computer:
> `$ hostnamectl`

- Set the hostname of the computer:
> `$ sudo hostnamectl set-hostname "{{hostname}}"`

- Set a pretty hostname for the computer:
> `$ sudo hostnamectl set-hostname --static "{{hostname.example.com}}" && sudo hostnamectl set-hostname --pretty "{{hostname}}"`

- Reset hostname to its default value:
> `$ sudo hostnamectl set-hostname --pretty ""`

---

Display one-line descriptions from manual pages.

- Display a description from a man page:
> `$ whatis {{command}}`

- Don't cut the description off at the end of the line:
> `$ whatis --long {{command}}`

- Display descriptions for all commands matching a glob:
> `$ whatis --wildcard {{net*}}`

- Search man page descriptions with a regular expression:
> `$ whatis --regex '{{wish[0-9]\.[0-9]}}'`

---
