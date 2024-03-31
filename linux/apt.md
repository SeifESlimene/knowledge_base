# ==Useful APT Commands==

- Update the list of available packages and versions:
> `$ apt update`

- Search for a given package:
> `$ apt search {{package}}`

- Install a package, or update it to the latest available version:
> `$ apt install {{package}}`

- Show information for a package:
> `$ apt show {{package}}`

- Upgrade all installed packages to their newest available versions:
> `$ apt upgrade`

- Remove a package:
> `$ apt remove {{package}}`

- Remove package with associated configuration:
> `$ apt purge {{package}}`

- List installed packages:
> `$ apt list --installed`

- List all packages:
> `$ apt list`

- Remove dependencies that were installed with applications and are no longer used by anything else on the system:
> `$ apt autoremove`

- Show all apt sources in a clean fashion:
> `$ egrep -v '^#|^ *$' /etc/apt/sources.list /etc/apt/sources.list.d/*`
