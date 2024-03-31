## ==Log Commands==

Write the kernel messages to standard output

- Show kernel messages:
> `$ dmesg`

- Show kernel error messages:
> `$ dmesg --level err`

- Show kernel messages and keep reading new ones, similar to tail -f (available in kernels 3.5.0 and newer):
> `$ dmesg -w`

- Show how much physical memory is available on this system:
> `$ dmesg | grep -i memory`

- Show kernel messages 1 page at a time:
> `$ dmesg | less`

- Show kernel messages with a timestamp (available in kernels 3.5.0 and newer):
> `$ dmesg -T`

- Show kernel messages in human-readable form (available in kernels 3.5.0 and newer):
> `$ dmesg -H`

- Colorize output (available in kernels 3.5.0 and newer):
> `$ dmesg -L`

---

Query the systemd journal

- Show all messages from this [b]oot:
> `$ journalctl -b`

- Show all messages from last [b]oot:
> `$ journalctl -b -1`

- Show all messages with priority level 3 (errors) from this [b]oot:
> `$ journalctl -b --priority={{3}}`

- [f]ollow new messages (like tail -f for traditional syslog):
> `$ journalctl -f`

- Show all messages by a specific [u]nit:
> `$ journalctl -u {{unit}}`

- Filter messages within a time range (either timestamp or placeholders like "yesterday"):
> `$ journalctl --since {{now|today|yesterday|tomorrow}} --until {{YYYY-MM-DD HH:MM:SS}}`

- Show all messages by a specific process:
> `$ journalctl _PID={{pid}}`

- Show all messages by a specific executable:
> `$ journalctl {{path/to/executable}}`
