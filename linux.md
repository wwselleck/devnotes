# Linux

- 📝 [Linux System Administration Basics](https://www.linode.com/docs/tools-reference/basics/linux-system-administration-basics/)
- 📝 [How To Configure a Linux Service](https://www.digitalocean.com/community/tutorials/how-to-configure-a-linux-service-to-start-automatically-after-a-crash-or-reboot-part-1-practical-examples)

## Boot

The boot process depends on the kind of firmware installed on the motherboard, generally BIOS or UEFI. UEFI is the newer of the two.

### UEFI (Unified Extensible Firmware Interface)
UEFI launches EFI applications, usually stored in the EFI partition.

#### GPT
GUID Parition Table (GPT) is a paritioning scheme designed to replace the traditional Master Boot Record (MBR). It is a table of entries defining partitions in the disk and the info associated with them (partition type, name, attributes)
#### Advantages over MBR
- MBR table entries are limited to a max size of 2 TiB, due to block addresses being 32 bits. GPT addresses are 64 bits, allowing a max disk size of 9.4 ZB.

#### EFI Partition
The EFI partition is often the first partition on the disk
The EFI applications are stored in `/EFI/vendor_name`.

#### Boot Process
- Power On Self Test (POST)
Checks that memory, cpu, etc is operating correctly

- Hardware is initialized (keyboard, mouse, etc)



###### References
https://wiki.archlinux.org/index.php/Arch_boot_process
https://wiki.archlinux.org/index.php/Partitioning#GUID_Partition_Table
http://www.linux-magazine.com/Online/Features/Coping-with-the-UEFI-Boot-Process
