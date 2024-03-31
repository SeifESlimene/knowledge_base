# ==Useful Git Commands==

List detailed information about hardware configurations as root user

- Launch the GUI:
> `$ sudo lshw -X`

- List all hardware in tabular format:
> `$ sudo lshw -short`

- List all disks and storage controllers in tabular format:
> `$ sudo lshw -class disk -class storage -short`

- Save all network interfaces to an HTML file:
> `$ sudo lshw -class network -html > {{interfaces.html}}`

---

Lists information about devices

 - List all storage devices in a tree-like format:
> `$ lsblk`

 - Also list empty devices:
> `$ lsblk -a`

 - Print the SIZE column in bytes rather than in a human-readable format:
> `$ lsblk -b`

 - Output info about filesystems:
> `$ lsblk -f`

 - Use ASCII characters for tree formatting:
> `$ lsblk -i`

 - Output info about block-device topology:
> `$ lsblk -t`

 - Exclude the devices specified by the comma-separated list of major device numbers:
> `$ lsblk -e {{1,7}}`

 - Display a customized summary using a comma-separated list of columns:
> `$ lsblk --output {{NAME}},{{SERIAL}},{{MODEL}},{{TRAN}},{{TYPE}},{{SIZE}},{{FSTYPE}},{{MOUNTPOINT}}`

---

how hardware information in GUI

> `$ sudo hardinfo`

- Start hardinfo:
> `$ hardinfo`

- Print report to standard output:
> `$ hardinfo -r`

- Save report to HTML file:
> `$ hardinfo -r -f html > hardinfo.html`

---

List SCSI devices (or hosts) and their attributes

- List all SCSI devices:
> `$ lsscsi`

- List all SCSI devices with detailed attributes:
> `$ lsscsi -L`

- List all SCSI devices with human-readable disk capacity:
> `$ lsscsi -s`

---

Display information about USB buses and devices connected to them

> `$ sudo lsusb`

- List all the USB devices available:
> `$ lsusb`

- List the USB hierarchy as a tree:
> `$ lsusb -t`

- List verbose information about USB devices:
> `$ lsusb --verbose`

- List detailed information about a USB device:
> `$ lsusb -D {{device}}`

- List devices with a specified vendor and product ID only:
> `$ lsusb -d {{vendor}}:{{product}}`

---

Provides access to an entire filesystem in one directory.

- Show all mounted filesystems:
> `$ mount`

- Mount a device to a directory:
> `$ mount -t {{filesystem_type}} {{path/to/device_file}} {{path/to/target_directory}}`

- Mount a CD-ROM device (with the filetype ISO9660) to /cdrom (readonly):
> `$ mount -t {{iso9660}} -o ro {{/dev/cdrom}} {{/cdrom}}`

- Mount all the filesystem defined in /etc/fstab:
> `$ mount -a`

- Mount a specific filesystem described in /etc/fstab (e.g. /dev/sda1 /my_drive ext2 defaults 0 2):
> `$ mount {{/my_drive}}`

- Mount a directory to another directory:
> `$ mount --bind {{path/to/old_dir}} {{path/to/new_dir}}`

---

A program for managing partition tables and partitions on a hard disk

> `$ sudo fdisk -lm`

- List partitions:
> `$ sudo fdisk -l`

- Start the partition manipulator:
> `$ sudo fdisk {{/dev/sdX}}`

- Once partitioning a disk, create a partition:
> `n`

- Once partitioning a disk, select a partition to delete:
> `d`

- Once partitioning a disk, view the partition table:
> `p`

- Once partitioning a disk, write the changes made:
> `w`

- Once partitioning a disk, discard the changes made:
> `q`

- Once partitioning a disk, open a help menu:
> `m`


---

View a disk's SMART data and other information

- View SMART health summary:
> `$ sudo smartctl --health {{/dev/sdX}}`

- View device information:
> `$ sudo smartctl --info {{/dev/sdX}}`

- Begin a short self-test:
> `$ sudo smartctl --test short {{/dev/sdX}}`

- View current/last self-test status and other SMART capabilities:
> `$ sudo smartctl --capabilities {{/dev/sdX}}`

- View SMART self-test log (if supported):
> `$ sudo smartctl --log selftest {{/dev/sdX}}`

---
