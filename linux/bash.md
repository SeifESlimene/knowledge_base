# ==Useful Bash Commands==

Provides certain LSB (Linux Standard Base) and distribution-specific information

- Print all available information:
> `$ lsb_release -a`

- Print a description (usually the full name) of the operating system:
> `$ lsb_release -d`

- Print only the operating system name (ID), suppressing the field name:
> `$ lsb_release -i -s`

- Print the release number and codename of the distribution, suppressing the field names:
> `$ lsb_release -rcs`

---

> `$ ps -f 1`
- Parent processes start child processes, so when we run "ls -l" the current process which is bash is forked into two, then the copy of itself was replaced by ls.
- fork an exec (first forks which makes a copy then exec replace the process with another process).
- exec replaces the current process.

---

##### Check if you are using UEFI or BIOS on Linux:
> `$ ls /sys/firmware/efi`
- /sys/firmware/efi exists means system uses UEFI

---

Manipulate the UEFI Boot Manager

- List the current settings / bootnums:
> `$ efibootmgr`

- List the filepaths:
> `$ efibootmgr -v`

- Add UEFI Shell v2 as a boot option:
> `$ sudo efibootmgr -c -d {{/dev/sda1}} -l {{\EFI\tools\Shell.efi}} -L "{{UEFI Shell}}"`

- Change the current boot order:
> `$ sudo efibootmgr -o {{0002,0008,0001,0005}}`

- Delete a boot option:
> `$ sudo efibootmgr -b {{0008}} --delete-bootnum`

---

/usr/share/X11/xkb/symbols/
/usr/share/X11/xkb/rules/xorg
/usr/lib/kbd/keymaps/xkb/fr.map.gz

---

##### Enable/Diasble KVM

> `$ cd /etc/modprobe.d/`
> `$ sudo nano blacklist.conf`

###### Add these to lines
`blacklist kvm_amd`
`install kvm_amd /bin/true`

###### And then reboot

> `$ reboot`

---

dconf dump /org/gnome/gnome-system-monitor/

dconf reset -f /org/gnome/gnome-system-monitor

dconf-editor

---

chrome://inspect/#devices

---

Displays or manipulates the directory stack.The directory stack is a list of recently visited directories that can be manipulated with the pushd and popd commands

- Display the directory stack with a space between each entry:
> `$ dirs`

- Display the directory stack with one entry per line:
> `$ dirs -p`

- Display only the nth entry in the directory stack, starting at 0:
> `$ dirs +{{N}}`

- Clear the directory stack:
> `$ dirs -c`

---

Place a directory on a stack so it can be accessed later

- Switch to directory and push it on the stack:
> `$ pushd {{directory}}`

- Switch first and second directories on the stack:
> `$ pushd`

- Rotate stack by making the 5th element the top of the stack:
> `$ pushd +4`

---

Remove a directory placed on the directory stack via the pushd shell built-in

- Remove the top directory from the stack and cd to it:
> `$ popd`

- Remove the Nth directory (starting from zero to the left from the list printed with dirs):
> `$ popd +N`

- Remove the Nth directory (starting from zero to the right from the list printed with dirs):
> `$ popd -N`

---

Sends a signal to a process, usually related to stopping the process.All signals except for SIGKILL and SIGSTOP can be intercepted by the process to perform a clean exit

- Terminate a program using the default SIGTERM (terminate) signal:
> `$ kill {{process_id}}`

- List available signal names (to be used without the SIG prefix):
> `$ kill -l`

- Terminate a background job:
> `$ kill %{{job_id}}`

- Terminate a program using the SIGHUP (hang up) signal. Many daemons will reload instead of terminating:
> `$ kill -{{1|HUP}} {{process_id}}`

- Terminate a program using the SIGINT (interrupt) signal. This is typically initiated by the user pressing Ctrl + C:
> `$ kill -{{2|INT}} {{process_id}}`

- Signal the operating system to immediately terminate a program (which gets no chance to capture the signal):
> `$ kill -{{9|KILL}} {{process_id}}`

- Signal the operating system to pause a program until a SIGCONT ("continue") signal is received:
> `$ kill -{{17|STOP}} {{process_id}}`

- Send a SIGUSR1 signal to all processes with the given GID (group id):
> `$ kill -{{SIGUSR1}} -{{group_id}}`

---

#!/bin/bash

# Compound Comparaison
if [ "$1" == Seif -a "$2" == Eddine -o "$3" == Slimene ]; then
  echo "Hatha Ismi S7i7!"
else
  echo "La 8alet!"
fi

# Integer Comparaison
if (("$3" < 6)); then
  echo "Right Answer!"
else
  echo "Wrong Answer!"
fi
