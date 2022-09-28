# Linux Foundation Certified System Administrator (LFCS)

![](https://training.linuxfoundation.org/wp-content/uploads/2020/11/lfcs_111820-300x300.png)

## TODOS

- [ ] Write down content of powerpoint
- [ ] Write down lab questions and answers



## Table of Contents

- [Essential commands](#essential-commands)
  * [Log into & remote graphical and text mode consoles](#log-into-remote-graphical-and-text-mode-consoles)
  * [Read and use System Documentation](#read-and-use-system-documentation)
  * [Create, Delete, Copy and Move Files and Directories](#create-delete-copy-and-move-files-and-directories)
  * [Create and manage hard links](#create-and-manage-hard-links)
  * [Create and manage soft links](#create-and-manage-soft-links)
  * [List, set and change standard file permissions](#list-set-and-change-standard-file-permissions)
  * [SUID, SGID, and Sticky Bit](#suid-sgid-and-sticky-bit)
  * [Search for files](#search-for-files)
  * [Compare and manipulate content](#compare-and-manipulate-content)
  * [Search file using Grep](#search-file-using-grep)
  * [Analyze test using basic regualar expressions](#analyze-test-using-basic-regualar-expressions)
  * [Extended Regular Expression](#extended-regular-expression)
  * [Archive, backup, compress, unpack, and uncompress files](#archive-backup-compress-unpack-and-uncompress-files)
  * [Compress and Uncompress files](#compress-and-uncompress-files)
  * [Backup files to a Remote System](#backup-files-to-a-remote-system)
  * [Use input output redirection](#use-input-output-redirection)
  
- [Operation of running systems](#operation-of-running-systems)
  * [Boot, reboot, and shutdown a system safely](#boot-reboot-and-shutdown-a-system-safely)
  * [Boot or change system into different operating modes](#boot-or-change-system-into-different-operating-modes)
  * [Install, configure and troubleshoot bootloaders](#install-configure-and-troubleshoot-bootloaders)
  * [Use scripting to automate system maintenance tasks](#use-scripting-to-automate-system-maintenance-tasks)
  * [Manage the startup process and service (In Services Configuration)](#manage-the-startup-process-and-service---in-services-configuration)
  * [Diagnose and manage processes](#diagnose-and-manage-processes)
  * [Locate and analyze system log files](#locate-and-analyze-system-log-files)
  * [Schedule tasks to run a set date and time](#schedule-tasks-to-run-a-set-date-and-time)
  * [Verify completion of scheduled jobs](#verify-completion-of-scheduled-jobs)
  * [Update software to provide required functionality and security](#update-software-to-provide-required-functionality-and-security)
  * [Manage Software](#manage-software)
  * [Identify the component of a Linux distribution that a file belongs to](#identify-the-component-of-a-linux-distribution-that-a-file-belongs-to)
  * [Verify the integrity and availability of resources](#verify-the-integrity-and-availability-of-resources)
  * [Change kernel runtime parameters, persistent and non-persistent](#change-kernel-runtime-parameters-persistent-and-non-persistent)
  * [List and Identify SELinux AppArmor file and process contexts](#list-and-identify-selinux-apparmor-file-and-process-contexts)
  
- [User and Group Management](#user-and-group-management)
  * [Create, delete, and modify local user accounts](#create-delete-and-modify-local-user-accounts)
  * [Create, delete, and modify local groups and group memberships](#create-delete-and-modify-local-groups-and-group-memberships)
  * [Manage system-wide enviroment profiles](#manage-system-wide-enviroment-profiles)
  * [Manage template user enviroment](#manage-template-user-enviroment)
  * [Configure user resource limits](#configure-user-resource-limits)
  * [Manage user privileges](#manage-user-privileges)
  * [Manage access to the root account](#manage-access-to-the-root-account)
  * [Configure PAM](#configure-pam)

- [Networking](#networking)
  * [Configure netowrking and hostname resolution statically or dynamically](#configure-netowrking-and-hostname-resolution-statically-or-dynamically)
  * [Configure network services to start automatically at reboot](#configure-network-services-to-start-automatically-at-reboot)
  * [Start, stop, and check the status of network services](#start-stop-and-check-the-status-of-network-services)
  * [Implement packet filtering](#implement-packet-filtering)
  * [Statically route IP traffic](#statically-route-ip-traffic)
  * [Synchronize time using other network peers](#synchronize-time-using-other-network-peers)

- [Service Configuration](#service-configuration)
  * [Configire a caching DNS server](#configire-a-caching-dns-server)
  * [Maintain a DNS zone](#maintain-a-dns-zone)
  * [Configure email aliases](#configure-email-aliases)
  * [Configure an IMAP and IMAPS service](#configure-an-imap-and-imaps-service)
  * [Configure SSH servers and clients](#configure-ssh-servers-and-clients)
  * [Restrict access to the HTTP proxy server](#restrict-access-to-the-http-proxy-server)
  * [Configure an HTTP server](#configure-an-http-server)
  * [Configure HTTP server log files](#configure-http-server-log-files)
  * [Restrict access to a web page](#restrict-access-to-a-web-page)
  * [Configure a database server](#configure-a-database-server)
  * [Manage and configure containers](#manage-and-configure-containers)
  * [Manage and configure Vertual Machines](#manage-and-configure-vertual-machines)

- [Storage Management](#storage-management)
  * [List, create, delete, and modify physical storage partitions](#list-create-delete-and-modify-physical-storage-partitions)
  * [Configure and manage swap space](#configure-and-manage-swap-space)
  * [Create and configure file systems](#create-and-configure-file-systems)
  * [Configure systems to mount file systems at or during boot](#configure-systems-to-mount-file-systems-at-or-during-boot)
  * [Evaluate and compare the basic file system feature and options](#evaluate-and-compare-the-basic-file-system-feature-and-options)
  * [Manage and configure LVM storage](#manage-and-configure-lvm-storage)
  * [Create and configure excrypted storage](#create-and-configure-excrypted-storage)
  * [Create and manage RAID devices](#create-and-manage-raid-devices)
  * [Setup user and group disk quotes for filesystems](#setup-user-and-group-disk-quotes-for-filesystems)



# Essential commands

## Log into remote graphical and text mode consoles
```console
$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group
default qlen 1000
link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
inet 127.0.0.1/8 scope host lo
valid_lft forever preferred_lft forever
inet6 ::1/128 scope host
valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state
UP group default qlen 1000
link/ether 08:00:27:6b:d7:87 brd ff:ff:ff:ff:ff:ff
inet 192.168.0.17/24 brd 192.168.0.255 scope global dynamic
noprefixroute enp0s3
valid_lft 1966sec preferred_lft 1966sec
inet6 fe80::a00:27ff:fe6b:d787/64 scope link noprefixroute
```
```console
$ ssh user@ip
Activate the web console with: systemctl enable --now cockpit.socket
Last login: Tue Oct 19 20:27:15 2021 from 192.168.0.3
```
## Read and use System Documentation
```console
$ ls --help
$ ls -l
$ journalctl --help
$ man journalctl
$ man man
$ man 1 printf
$ man 3 printf
$ apropos directory
$ sudo mandb
$ apropos director
$ systemctl                             [TAB TAB TAB]
$ systemctl list -dependecies           [TAB]
```
## Create Delete Copy and Move Files and Directories
### Current / Working Directory
```console
$ ls
$ ls -a
$ ls -l /var/log/
$ ls -al
$ ls -alh
$ pwd
$ cd /var/log/
$ cd ..
4 cd /
$ cd -
$ cd
```
### Creating Files 
```console
$ touch file.txt
$ touch /home/bob/file.txt
$ touch ../bob/file.txt
```

### Creating Directories
```console
$ mkdir Files
```

### Moving Files and Directories
```console
$ cp file.txt Files/
$ cp -r Files/ BackupFiles/
```

### Moving Files
```console
$ mv file.txt Files/
```

### Deleting Files and Directories
```console
$ rm files.txt
$ rm -r Files/
```
## Create and manage hard links
### Inodes
```console
$ echo “Picture of Milo the dog” > Pictures/family_dog.jpg
$ stat Pictures/family_dog.jpg
File: Pictures/family_dog.jpg
Size: 49 Blocks: 8 IO Block: 4096 regular file
Device: fd00h/64768d Inode: 52946177 Links: 1
Access: (0640/-rw-r-----) Uid: ( 1000/ aaron) Gid: ( 1005/ family)
Context: unconfined_u:object_r:user_home_t:s0
Access: 2021-10-27 16:33:18.949749912 -0500
Modify: 2021-10-27 14:41:19.207278881 -0500
Change: 2021-10-27 16:33:18.851749919 -0500
Birth: 2021-10-26 13:37:17.980969655 -0500
```
### Hard Links
```console
$ cp –r /home/aaron/Pictures/ /home/jane/Pictures/
$ ln /home/aaron/Pictures/family_dog.jpg /home/jane/Pictures/family_dog.jpg
# ln path_to_target_file path_to_link_file

$ stat Pictures/family_dog.jpg
File: Pictures/family_dog.jpg
Size: 49 Blocks: 8 IO Block: 4096 regular file
Device: fd00h/64768d Inode: 52946177 Links: 2
Access: (0640/-rw-r-----) Uid: ( 1000/ aaron) Gid: ( 1005/ family)
Context: unconfined_u:object_r:user_home_t:s0
Access: 2021-10-27 16:33:18.949749912 -0500
Modify: 2021-10-27 14:41:19.207278881 -0500
Change: 2021-10-27 16:33:18.851749919 -0500
Birth: 2021-10-26 13:37:17.980969655 -0500

$ rm /home/aaron/Pictures/family_dog.jpg
$ rm /home/jane/Pictures/family_dog.jpg
```
### Limitations and Considerations
```console
$ useradd –a –G family aaron
$ useradd –a –G family jane
$ chmod 660 /home/aaron/Pictures/family_dog.jpg
```

## Create and manage soft links
```console
# ln -s path_to_target_file path_to_link_file
$ ln –s /home/aaron/Pictures/family_dog.jpg family_dog_shortcut.jpg
$ ls -l
lrwxrwxrwx. 1 aaron aaron family_dog_shortcut.jpg -> /home/aaron/Pictures..
$ readlink family_dog_shortcut.jpg
/home/aaron/Pictures/family_dog.jpg
$ echo “Test” >> fstab_shortcut
bash: fstab_shortcut: Permission denied
$ ls -l
lrwxrwxrwx. 1 aaron aaron family_dog_shortcut.jpg -> /home/aaron/Pictures..
```
## List set and change standard file permissions

### Owners and Groups
```console
$ ls -l
$ chgrp wheel picture.jpg
$ ls -l 
-rw-r-----. 1 bob wheel 49 Oct 27 14:41 picture.jpg
$ groups
$ sudo chown jane picture.jpg
$ ls -l 
-rw-r-----. 1 jane family 49 Oct 27 14:41 picture.jpg
$ sudo chown bob:family picture.jpg
$ ls -l
-rw-r-----. 1 bob family 49 Oct 27 14:41 picture.jpg
```
### File and Directory Permissions
```console
$ ls -l
-rwxrwxrwx. 1 bob family 49 Oct 27 14:41 picture.jpg
```

| File Type        | Identifier |
| ---------------- | ----------:|
| Directory        |      d     |
| Regular File     |      -     |
| Character Device |      c     |
| Link             |      l     |
| Socket File      |      s     |
| Pipe             |      p     |
| Block Device     |      b     |

owner | group | others

### Adding Permissions
```console
$ chmod u+w picture.jpg
$ chmod o-r picture.jpg
$ chmod g=r picture.jpg
$ chmod g=rw text.txt
$ chmod g= text.txt
$ chmod g-rwx text.txt
$ chmod u+rw,g=r,o= text.txt
$ chmod u=rw,g-w text.txt
$ chmod 755 text.txt
```
### Octal Permission
| Permission | Value |
| ---------- | ----- |
|     r      |   4   |
|     w      |   2   |
|     x      |   1   |

## SUID SGID and Sticky Bit
```console
```
## Search for files
```console
$ find /usr/share/ -name '*.jpg'
$ find /lib64/ -size +10M
$ find /dev/ -mmin -1
$ find /bin/ -name file1.txt
$ find -name file1.txt              # No path -> current directory
$ find -iname bob
$ find -name "f*"
```
### Modified Time
```console
$ find -mmin [minute]
$ find -mmin 5
$ find -mmin -5
$ find -mmin +5
$ find -mtime 2                     # 24-hour periods
$ find -cmin -5                     # change Minute
```
### File Size
```console
$ find -size 512k
$ find -size +512k                  # Greater than 512 kb
$ find -size -512k                  # Less than 512 kb
```
### Search Expressions
```console
$ find -name "f*"
$ find -name "f*" -size 512k        # AND operator
$ find -name "f*" -o -size 512k     # OR operator
$ find -not -name "f*"              # NOT operator
$ find \! -name "*"                 # alternate NOT operator

$ find -perm 664                    # exactly 664 permissions
$ find -perm -664                   # at least 664 permissions
$ find -perm /664                   # any of these permissions
$ find -perm u=rw,g=rw,o=r          # exectly 664 permissions
$ find -perm -u=rw,g=rw,o=r         # at least 664 permissions
$ find -perm /u=rw,g=rw,o=r         # any of these permissions

$ find \! -perm -o=r
```
## Compare and manipulate content
```bash
$ cat users.txt
$ tac users.txt
$ tail /var/log/dnf.log
$ tail -n 20 dnf.log
$ head dnf.log
```
```bash
$ sed 's/canda/canada/g' userinfo.txt
$ sed 's/canda/canada' userinfo.txt
$ sed -i 's/canda/canada' userinfo.txt

$ cut -d ' ' -f 1 userinfo.txt         # cut first cell 
$ cut -d ',' -f 3 userinfo.txt         # cut third cell separated with ,

$ uniq countries.txt                   # delete double entries

$ sort countries
$ sort countries.txt | uniq

$ diff file1 file2                                 # difference
$ diff -c file1 file2                              # context
$ diff -y file1 file2     === $ sdiff file1 file2  # side-by-side diff
```

## Search file using Grep
```batch
$ grep 'CentOS' /etc/os-release
NAME="- CentOS Stream"
PRETTY_NAME="CentOS Stream 8"
REDHAT_SUPPORT_PRODUCT_VERSION="CentOS Stream"

$ grep 'centos' /etc/os-release
ID="centos"
CPE_NAME="cpe:/o:centos:centos:8"
HOME_URL="https://centos.org/"

$ grep -i 'centos' /etc/os-release                    # not case sensitive
NAME="CentOS Stream"
ID="centos"
PRETTY_NAME="CentOS Stream 8"
CPE_NAME="cpe:/o:centos:centos:8"
HOME_URL="https://centos.org/"
REDHAT_SUPPORT_PRODUCT_VERSION="CentOS Stream"

$ sudo grep -r 'CentOS' /etc/                          # recursive
/etc/centos-release:CentOS Stream release 8
/etc/krb5.conf.d/kcm_default_ccache:# On Fedora/RHEL/CentOS, this is /etc/krb5.conf.d/
grep: /etc/grub.d: Permission denied
/etc/yum.repos.d/CentOS-Stream-AppStream.repo:# CentOS-Stream-AppStream.repo
/etc/yum.repos.d/CentOS-Stream-AppStream.repo:# close to the client. You should use this for CentOS updates unless you are
/etc/yum.repos.d/CentOS-Stream-AppStream.repo:name=CentOS Stream $releasever - AppStream
/etc/yum.repos.d/CentOS-Stream-BaseOS.repo:# CentOS-Stream-BaseOS.repo

$ sudo grep -ir 'centos' /etc/                         # ignore case
/etc/dnf/vars/contentdir:centos
/etc/rpm/macros.dist:%centos_ver 8
/etc/rpm/macros.dist:%centos 8
/etc/lvm/archive/cs_00000-1586619700.vg:creation_host = "LFCS-CentOS" # Linux LFCS-CentOS 4.18.0-338.el8.x86_64 #1 SMP
Fri Aug 27 17:32:14 UTC 2021 x86_64
/etc/lvm/archive/cs_00000-1586619700.vg: creation_host = "LFCS-CentOS"
/etc/lvm/archive/cs_00000-1586619700.vg: creation_host = "LFCS-CentOS"
/etc/lvm/backup/cs:creation_host = "LFCS-CentOS" # Linux LFCS-CentOS 4.18.0-338.el8.x86_64 #1 SMP Fri Aug 27 17:32:14 UTC
2021 x86_64
/etc/lvm/backup/cs: creation_host = "LFCS-CentOS"
/etc/lvm/backup/cs: creation_host = "LFCS-CentOS"
/etc/centos-release:CentOS Stream release 8

$ grep -vi 'centos' /etc/os-release                    # --invert-match
VERSION="8"
ID_LIKE="rhel fedora"
VERSION_ID="8"
PLATFORM_ID="platform:el8"
ANSI_COLOR="0;31"
BUG_REPORT_URL="https://bugzilla.redhat.com/"
REDHAT_SUPPORT_PRODUCT="Red Hat Enterprise Linux 8"

$ grep -wi 'red' /etc/os-release                       # words
REDHAT_SUPPORT_PRODUCT="Red Hat Enterprise Linux 8"

$ grep -oi 'centos' /etc/os-release                    # --only-matching
CentOS
centos
CentOS
centos
centos
centos
CentOS
```

## Analyze test using basic regualar expressions
```console
$ grep '^PASS' /etc/login.defs                          # line begin with PASS
$ grep -v '^#' /etc/login.defs                          # invert | not line begin with #
$ grep '7$' /etc/login.defs                             # line ends with 7

$ grep -r 'c.t' /etc/                                   # all words include c and t
cat, cut, execute, concatenated
$ grep -wr 'c.t' /etc/                                  # only the word start with c and end with t
cut, cat

$ grep '.' /etc/login.defs                              # this looks not for special chars
$ grep '\.' /etc/login.defs                             # this looks for chars

$ grep -r 'let*' /etc/                                  # match previous element 0 or more times
files, silent, problem, leftmargin, left, letter, legal
$ grep -r '/.*/' /etc/                                  # begins with / and ends with /
/usr/, /varr/cache/, /etc/
$ grep -r '0*' /etc/                                    # Match previous 1 or more times
0000000, 231043

$ grep -r '0+' /etc/
KP0+
$ grep -r '0\+' /etc/
0, 0000, 270372, 1.0
$ grep -Er '0+' /etc/
0, 0000, 270372, 1.0
````

## Extended Regular Expression
```console
$ egrep -r '0+' /etc/
0, 0000, 270372, 1.0
````
### Previous Element can Exist this many Times
```console
$ egrep -r '0{3,}' /etc/
000
$ egrep -r '10,{,3}' /etc/
1.0, 160, 1, 100000, 10
$ egrep -r '0{3}' /etc/
000
$ egrep -r '0{3,5}' /etc/                        
000, 0000, 00000
````
### Make The Previous Element Optional
```console
$ egrep -r 'disbled?' /etc/
disble, disabled, disables
```

### Match One Thing Or The Other
```console
$ egrep -r 'enabled|disbled' /etc/
disbled, enabled
$ egrep -ir 'enabled?|disbled?' /etc/
Enabled, enabled, Disabled, disabled
```

### Ranges or Sets
[a-z] [0-9] [abz954]
```console
$ egrep -r 'c[au]t' /etc/                                     
cut, cat, deprecated, execute, shortcuts, cation

$ egrep -r '/dev/.*' /etc/
/etc/smartmontools/smartd.conf:#/dev/twl0 -d 3ware,0 -a -s L/../../2/01
/etc/smartmontools/smartd.conf:#/dev/twl0 -d 3ware,1 -a -s L/../../2/03
/etc/smartmontools/smartd.conf:#/dev/hdc,0 -a -s L/../../2/01
/etc/smartmontools/smartd.conf:#/dev/hdc,1 -a -s L/../../2/03

$ egrep -r '/dev/[a-z]*' /etc/
/etc/smartmontools/smartd.conf:#/dev/twl0 -d 3ware,0 -a -s L/../../2/01
/etc/smartmontools/smartd.conf:#/dev/hdc,0 -a -s L/../../2/01
/etc/smartmontools/smartd.conf:#/dev/hdc,1 -a -s L/../../2/03

$ egrep -r '/dev/[a-z]*[0-9]' /etc/
/etc/sane.d/v4l.conf:/dev/bttv0
/etc/sane.d/v4l.conf:/dev/video0
/etc/sane.d/v4l.conf:/dev/video1

$ egrep -r '/dev/[a-z]*[0-9]?' /etc/
/etc/smartmontools/smartd.conf:#/dev/twl0 -d 3ware,0 -a -s L/../../2/01
/etc/smartmontools/smartd.conf:#/dev/hdc,0 -a -s L/../../2/01
/etc/smartmontools/smartd_warning.sh: hostname=`eval $cmd 2>/dev/null` || continue
````
### Subexpressions
```console
$ egrep -r '/dev/[a-z]*[0-9]?' /etc/
/etc/sane.d/umax.conf:/dev/usbscanner
/etc/sane.d/epjitsu.conf:#usb /dev/usb/scanner0
/etc/sane.d/umax_pp.conf:# /dev/ppi1, ...
/etc/sane.d/fujitsu.conf:#scsi /dev/sg1

$ egrep -r '/dev/([]*[0-9]?)*' /etc/
/etc/sane.d/dc240.conf:port=/dev/ttyS0
/etc/sane.d/dc240.conf:#port=/dev/ttyd1
/etc/sane.d/dc240.conf:#port=/dev/term/a
/etc/sane.d/dc240.conf:#port=/dev/tty0p0
/etc/sane.d/dc240.conf:#port=/dev/tty01
/etc/sane.d/dc25.conf:port=/dev/ttyS0

$ egrep -r -r '/dev/(([a-z]|[A-Z])*[0-9]?)*' /etc/
/etc/sane.d/dc240.conf:port=/dev/ttyS0
/etc/sane.d/dc240.conf:#port=/dev/ttyd1
/etc/sane.d/dc240.conf:#port=/dev/term/a
```
### [^]: Negated Ranges Or Sets
```console
$ egrep -r 'http[^s]' /etc/                             # NOT https
http, httpd

$ egrep -r '/[^a-z]' /etc/                              # NOT lower case letters
/X, /4, /$, /., /
```

## Archive backup compress unpack and uncompress files

1. Archive (Packing) = backup.tar
2. Compress = backup.tar.gz
3. Backup

### Packing Files and Directories
```console
$ tar --list --file archive.tar
$ tar -tf archive.tar
$ tar tf archive.tar

$ tar --create --file archive.tar file1
# This is the same:
$ tar cf archive.tar file1

$ tar --append --file archive.tar file2 
# This is the same:
$ tar rf archive.tar file2

$ tar --create --file archive.tar Pictures/
$ tar --create --file archive.tar /home/bob/Pictures/

$ tar --list --file archive.tar 
# This is the same:
$ tar tf archive.tar

$ tar --extract --file archive.tar
# This is the same:
$ tar xf archive.tar

$ tar --extract --file archive.tar --directory /tmp/
# This is the same:
$ tar xf archive.tar -C /tmp/

$ sudo tar --extract --file archive.tar --directory /tmp/
```
## Compress and Uncompress files
```console
$ gzip file1
$ gunzip file1.gz
$ gzip --decompress file1.gz

$ bzip file2
$ bunzip file2.bz2
$ bzip2 --decompress file2.bz2

$ xz file3
$ unxz file3.xz 
$ xz --decompress file3.xz

$ gzip --keep file1
$ bzip2 --keep file2
$ xz --keep file3
$ gzip --list file1
compressed uncompressed ratio name
71 78 39.7% file1
```

### Compress And Decompression Utilities
```console
$ zip archive file 1
# This is the same:
$ zip archive.zip file1

$ zip -r archive.zip Pictures/                  # recursivly
$ unzip archive.zip

$ tar --create --file archive.tar file1
$ gzip archive.tar
$ gzip --keep archive.tar

$ tar --create --gzip --file archive.tar.gz file1
# This is the same:
$ tar czf archive.tar.gz file1

$ tar --create --bzip2 --file archive.tar.bz2 file1
# This is the same:
$ tar cjf archive.tar.bz2 file1

$ tar --create --xz --file archive.tar.xz file1
# This is the same:
$ tar cJf archive.tar.xz file1

$ tar caf archive file1
$ tar --ectract --file archive.tar.gz
$ tar xf archive.tar.gz file1
````

## Backup files to a Remote System
```console
$ rsync -a Pictures/ bob@9.9.9.9:/home/bib/Pictures/
$ rsync -a bob@9.9.9.9:/home/bib/Pictures/ Pictures/
$ rsync -a Pictures/ /Backup/Pictures/
```
### Disk Imaging
```console
$ sudo dd if=/dev/vda of=diskimage.raw bs=1M status=progress
1340080128 bytes (1.3GB, 1.2GB) copied, 3s, 432 MB/s
$ sudo dd if=diskimage.raw of=/dev/vda bs=1M status=progress
1340080128 bytes (1.3GB, 1.2GB) copied, 3s, 432 MB/s
```
## Use input output redirection
```console
$ cat file.txt
$ sort file.txt
$ sort file.txt > sortedfile.txt

$ date > file.txt                           # standard output stdout 
# This is the same:
$ date 1> file.txt

$ script.sh 2> errors.txt                   # standard error stderr
$ script.sh < input.txt                     # standard input stdin

$ script.sh 1> output.txt 2> errors.txt     # overwrite
$ script.sh 1>> output.txt 2>> errors.txt   # append

# This is all the same:
$ script.sh > output.txt 2>&1
$ script.sh 1> output.txt 2>&1
$ script.sh 2>&1 output.txt

$ sort <<EOF
> 6
> 3
> 8
> EOF
3
6
8

$ bc <<<1+2+3+4
10

# Piping
$ grep –v '^#' /etc/login.defs | sort | column -t
```

# Operation of running systems
## Boot reboot and shutdown a system safely
```console
$ systemctl reboot                             # system control
$ systemctl poweroff
$ systemctl reboot --force
$ systemctl poweroff --force
$ systemctl reboot --force --force
$ systemctl poweroff --force --force
$ shutdown 02:00
$ shutdown +15
$ shutdown -r 02:00
$ shutdown -r +15
$ shutdown  -r +1
```

## Boot or change system into different operating modes
missing
## Install configure and troubleshoot bootloaders
missing

## Use scripting to automate system maintenance tasks
### Use Scripting to Automate Tasks
```console
$ touch script.sh
$ chmod +x script.sh
$ ./script.sh
```
script.sh:
```bash
#!/bin/bash

#Log the date and time the script was last
executed
date >> /tmp/script.log
cat /proc/version >> /tmp/script.log

tar acf /tmp/archive.tar.gz /etc/dnf

if test -f /tmp/archive.tar.gz; then
    mv /tmp/archive.tar.gz
    /tmp/archive.tar.gz.OLD
    tar acf /tmp/archive.tar.gz /etc/dnf/
else
    tar acf /tmp/archive.tar.gz /etc/dnf/
fi

if grep -q '5' /etc/default/grub; then
    echo 'Grub has timeout of 5 seconds.'
else
    echo 'Grub DOES NOT have a timeout of 5 seconds.'
fi
```

```bash
#!/bin/sh
# Check whether 0anacron was run today already
if test -r /var/spool/anacron/cron.daily; then
    day=`cat /var/spool/anacron/cron.daily`
fi
if [ `date +%Y%m%d` = "$day" ]; then
    exit 0
fi
# Do not run jobs when on battery power
online=1
for psupply in AC ADP0 ; do
    sysfile="/sys/class/power_supply/$psupply/online"
    if [ -f $sysfile ] ; then
        if [ `cat $sysfile 2>/dev/null`x = 1x ]; then
            online=1
            break
        else
            online=0
        fi
    fi
done
if [ $online = 0 ]; then
    exit 0
fi
```
## Manage the startup process and service - In Services Configuration
### Start Process and Services
```console
$ systemctl cat sshd.service
$ systemctl edit --full sshd.service
$ systemctl revert sshd.service
$ systemctl status sshd.service
$ systemctl stop sshd.service
$ systemctl status sshd.service
$ systemctl restart sshd.service
$ systemctl reload sshd.service
$ systemctl reload-or-restart sshd.service
$ systemctl disable sshd.service
$ systemctl is-enabled sshd.service
disabled
$ systemctl enable sshd.service
$ systemctl enable --now sshd.service
$ systemctl disable --now sshd.service

$ systemctl mask sshd.service
$ systemctl status sshd.service
Failed to enable unit: Unit file /etc/systemd/system/atd.service is masked.
$ systemctl unmask sshd.service

$ $ systemctl list-units --type service --al
```
## Diagnose and manage processes
missing
## Locate and analyze system log files
```console
$ less file.log
$ tail -F file.log                                      # show all upcomming logs
```

### Journalctl
```console
$ journalctl /bin/sudo
$ journalctl -u sshd.service
$ journalctl
$ journalctl -e
Nov 16 18:40:01 LFCS-CentOS anacron[3666]: Job `cron.weekly' terminated
Nov 16 18:40:01 LFCS-CentOS anacron[3666]: Normal exit (2 jobs run)
lines 994-1016/1016 (END)
$ journalctl -f
$ journalctl -p err                                     # just error logs
$ journalctl -p                                         # TAB TAB will show you: info, warning, err, crit
$ journalctl -p -g '^b'
$ journalctl -S 02:00
$ journalctl -S 01:00 -U 02:00
$ journalctl -S '2021-11-16 12:04:55'
$ journalctl -b 0
$ journalctl -b -1
```
### See Who Logged In
```console
$ last 
$ lastlog
```
## Schedule tasks to run a set date and time
```console
$ cat /etc/crontab
SHELL=/bin/bash
PATH=/sbin:/bin:/usr/sbin:/usr/bin
MAILTO=root
# For details see man 4 crontabs
# Example of job definition:
# .---------------- minute (0 - 59)
# | .------------- hour (0 - 23)
# | | .---------- day of month (1 - 31)
# | | | .------- month (1 - 12) OR jan,feb,mar,apr ...
# | | | | .---- day of week (0 - 6) (Sunday=0 or 7) OR
sun,mon,tue,wed,thu,fri,sat
# | | | | |
# * * * * * user-name command to be executed
35 6 * * * root /bin/some_command --some_options
```
* = match all possible values (i.e., every hour)
, = match multiple values (i.e., 15,45)
- = range of values (i.e., 2-4)
/ = specifies steps (i.e., */4)

### Scheduling Jobs with cron
daily = /etc/cron.daily/
hourly = /etc/cron.hourly/
monthly = /etc/cron.monthly/
weekly = /etc/cron.weekly/

```console
$ which touch
$ crontab -e
$ crontab -l
35 6 * * * /usr/bin/touch bob_test
$ sudo crontab -l
0 * * * * /usr/bin/touch root_test
$ sudo crontab -e -u jane
30 * * * * /usr/bin/touch jane_test
$ crontab -r
$ sudo cronta -r -u jane
```

```console
$ touch shellscript 
$ sudo cp shellcript /etc/cron.hourly/
$ sudo chmod -rx /etc/cron.hourly/shellcript
$ sudo rm /etc/cron.hourly/shellscript
```
### Scheduling Jobs with anacron
```console
$ sudo vim /etc/anacrontab
#period in days delay in minutes job-identifier command
1 5 cron.daily nice run-parts
/etc/cron.daily
7 25 cron.weekly nice run-parts
/etc/cron.weekly
@monthly 45 cron.monthly nice run-parts /etc/cron.monthly
3 10 test job /usr/bin/touch /root/anacron_created_this
7 10 test job /usr/bin/touch /root/anacron_created_this
@weekly 10 test job /usr/bin/touch /root/anacron_created_this
@monthly 10 test job /usr/bin/touch /root/anacron_created_this

$ anacron -T
```
### Scheduling Jobs with at
```console
$ sudo -i                                   # execute as root
$ at 15:00
$ at 'August 20 2022'
at> /usr/bin/touch atscheduler              # CTL+D
$ at '2:30 August 20 2022'
$ at 'now + 30 minutes'
$ at 'now + 3 hours'
$ at 'now + 3 days'
$ at 'now + 3 weeks'
$ at 'now + 3 months'

$ atq
$ at -c 20 
$ atrm 20
```
## Verify completion of scheduled jobs
missing 

```console
$ sudo anacron -n -f 
```
## Update software to provide required functionality and security
```console
$ dnf check-upgrade
$ sudo dnf upgrade
````

## Manage Software
```console
$ sudo dnf repolist
repo id repo name
appstream CentOS Stream 8 - AppStream
baseos CentOS Stream 8 - BaseOS
extras CentOS Stream 8 - Extras

$ sudo dnf repolist -v                          # verbose
$ sudo dnf repolist --all
$ sudo dnf config-manager -enable powertools
$ sudo dnf config-manager -disable powertools
$ sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

$ sudo dnf repolist -v
Repo-filename : /etc/yum.repos.d/docker-ce.repo
$ sudo rm /etc/yum.repos.d/docker-ce.repo

$ sudo search web server
cockpit.x86_64: Web Console for Linux servers
$ sudo search 'web server'
nginx.x86_64: A high performance web server and reverse proxy server

$ sudo dnf info nginx
Description : Nginx is a web server and a reverse proxy server for HTTP, SMTP,
POP3 and
: IMAP protocols, with a strong focus on high concurrency,
performance and low
: memory usage.

$ sudo dnf install nginx
$ sudo dnf reinstall nginx
$ sudo dnf remove nginx

$ sudo dnf group list 
Available Environment Groups:
Server
Minimal Install
Workstation
Virtualization Host
Custom Operating System
Server with GUI
$ sudo dnf group install 'Server with GUI'
$ sudo dnf group install --with-optional 'Server with GUI'
$ sudo dnf group remove 'Server with GUI'

$ sudo dnf group list --hidden

$ wget https://download.nomachine.com/download/7.7/Linux/nomachine_7.7.4_1_x86_64.rpm
$ sudo dnf install ./nomachine_7.7.4_1_x86_64.rpm
$ sudo dnf remove nomachine
$ sudo dnf autoremove
$ sudo dnf history
$ sudo dnf                                # TAB TAB y => display all possibilities
```

## Identify the component of a Linux distribution that a file belongs to 
```console
$ dnf provides /etc/anacrontab
$ sudo rm /etc/anacrontab
$ dnf reinstall cronie-anacron
$ dnf provides docker
$ dnf repoquery --list nginx
$ dnf repoquery -l nginx | grep conf
```
## Verify the integrity and availability of resources
### Verify Key Resources and Processes
```console
$ df
$ du -sh /bin/
$ df -h
$ free -h
$ uptime
$ lspci 
$ lscpu
$ sudo xfs_repair -v /dev/vdb1
$ sudo fsck.ext4 -v -f -p /dev/vdb2

$ systemctl list-dependencies
$ sudo pkill chronyd
```
## Change kernel runtime parameters, persistent and non-persistent

```console
$ sudo sysctl -a
net.ipv6.conf.default.disable_ipv6 = 0
$ sudo sysctl -w net.ipv6.conf.default.disable_ipv6=1
$ sudo sysctl -w net.ipv6.conf.default.disable_ipv6

$ man sysctl.d
$ sysctl -a | grep vm
vm.panic_on_oom = 0
vm.percpu_pagelist_fraction = 0
vm.stat_interval = 1
vm.swappiness = 30

$ sudo vim /etc/sysctl.d/swap-less.conf
$ sudo sysctl -p /etc/sysctl.d/swap-less.conf
```

## List and Identify SELinux AppArmor file and process contexts

```console
$ ls -l
-rw-rw-r--. 1 aaron aaron 160 Dec 1 18:19 archive.tar.gz

$ ls -Z
unconfined_u:object_r:user_home_t:s0 archive.tar.gz
```

unconfined_u:object_r:user_home_t:s0
    user       role     type      level

1. Only certain users can enter certain roles and certain types.
2. It lets authorized users and processes do their job, by granting the
permissions they need.
3. Authorized users and processes are allowed to take only a limited
set of actions.
4. Everything else is denied. 

```console
$ ps axZ
system_u:system_r:accountsd_t:s0 995 ? Ssl 0:00 /usr/libexec/accoun
system_u:system_r:NetworkManager_t:s0 1024 ? Ssl 0:00 /usr/sbin/NetworkMa
system_u:system_r:sshd_t:s0-s0:c0.c1023 1030 ? Ss 0:00 /usr/sbin/sshd -D -
system_u:system_r:tuned_t:s0 1032 ? Ssl 0:00 /usr/libexec/platfo
system_u:system_r:cupsd_t:s0-s0:c0.c1023 1033 ? Ss 0:00 /usr/sbin/cupsd -l

$ ls -Z /usr/sbin/sshd
system_u:object_r:sshd_exec_t:s0 /usr/sbin/sshd

$ ps axZ
unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023 1875 ? Ss 0:00 /usr/lib/
system_u:system_r:init_t:s0 1881 ? S 0:00 (sd-pam)
unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023 1891 ? Ssl 0:00 /usr/bin

$ id -Z

$ sudo semanage login -l
Login Name SELinux User MLS/MCS Range Service
__default__ unconfined_u s0-s0:c0.c1023 *
root unconfined_u s0-s0:c0.c1023 *

$ sudo semanage user -l
SELinux User Prefix MCS Level MCS Range SELinux Roles
guest_u user s0 s0 guest_r
root user s0 s0-s0:c0.c1023 staff_r sysadm_r system_r unconfined_r
staff_u user s0 s0-s0:c0.c1023 staff_r sysadm_r unconfined_r
sysadm_u user s0 s0-s0:c0.c1023

$ getenforce
$ sudo setenforce 1

$ sudo chcon -t httpd_sys_content_t /var/index.html
```

#### Enforcing, Permissive, Disabled
------

# User and Group Management
## Create delete and modify local user accounts
```console
$ sudo useradd john
$ ls -a /etc/skel

$ useradd --defaults
# This is the same:
$ useradd -D

$ cat /etc/login.defs
$ sudo passwd john
$ sudo userdel john
$ sudo userdel --remove john
# This is the same:
$ sudo userdel -r john
$ sudo useradd --sehll /bin/othershell --home-dir /home/otherdirectory/ john
$ sudo useradd -s /bin/othershell -d /home/otherdirectory/ john
$ sudo useradd -s /bin/othershell john

$ cat /etc/passwd
$ sudo useradd --uid 1100 smith
# This is the same:
$ sudo useradd -u 1100 smith
$ ls -ln
$ id
$ whoami
$ sudo useradd --system sysacc

$ sudo usermod --home /home/bla --move-home john
$ sudo usermod -d /home/bla -m john
$ sudo usermod --login jane john 
# This is the same:
$ sudo usermod -l jane john
$ sudo usermod --shell /bin/bla jane
# This is the same:
$ sudo usermod -s /bin/bla jane

$ sudo usermod --lock jane
SAME: $ usermod -L jane
$ usermod --unlock jane
SAME: $ usermod -U jane
$ usermod --expiredare 2021-12-10 jane
SAME: $ usermod -e 2021-12-10 jane
$ usermod --expire "" jane
SAME: $ usermod -e "" jane

$ chage --lastday 0 jane
SAME: $ chage -d 0 jane
$ chage --lastday -1 jane
SAME: $ chage -d -1 jane
$ chage --maxdays 30 jane
SAME: $ chage -M 30 jane
$ chage --maxdays -1 jane
SAME: $ chage -M -1 jane
$ chage --list jane
SAME: $ chage -l jane

$ groupadd --gid 9873 cricket
$ groupdel john
```
## Create delete and modify local groups and group memberships 
```console
$ sudo gpasswd --add john developers
$ sudo gpasswd --a john developers
$ groups john
john: john developers
$ sudo gpasswd --delete john developers
$ sudo gpasswd -d john developers

$ sudo usermod -g developers john
$ sudo usermod --gid developers john
$ groups john
john: developers
$ gpasswd --help
-a, --add USER add USER to GROUP

$ sudo groupmod --new-name programmers developers
$ sudo groupmod -n programmers developers
$ sudo groupdel programmers
groupdel: cannot remove the primary group of user 'john'
$ sudo usermod --gid john john
$ sudo groupdel programmers
```
## Manage system-wide enviroment profiles
```console
$ printenv
PATH=/home/aaron/.local/bin:/home/aaron/bin:/usr/local/bin:/usr/local/sbin
:/usr/bin:/usr/sbin
HISTSIZE=1000
GJS_DEBUG_TOPICS=JS ERROR;JS LOG
SESSION_MANAGER=local/unix:@/tmp/.ICE-unix/2260,unix/unix:/tmp/.ICEunix/2260

SAME:$ env

$ HISTSIZE=2000
$ history

$ echo $HOME
$ sudo vim /etc/environment
> KODEKLOUD=https://kodekloud.com
$ echo $KODEKLOUD

$ sudo vim /etc/profile.d/lastlogin.sh 
> echo "Your last login was at: " >
> $HOME/lastlogin
> date >> $HOME/lastlogin 
$ logout
$ ls
lastlogin
$ cat lastlogin
Your last login was at: Thursday DEC 16 11:19:27 CDT 2021

$ sudo vi /etc/profile.d/welcome.sh
> echo "next login will show this text"
```
## Manage template user enviroment 
```console
$ sudo vim /home/trinity/.bashrc
> PATH="$HOME/.local/bin:$HOME/bi
> n:$PATH"
> PATH="$HOME/.local/bin:$HOME/bin
> :/opt/bin:$PATH"
$ echo $PATH
/home/trinity/.local/bin:/home/trinity/bin:/usr/local/bin:/usr/bin:/usr
/local/sbin:/usr/sbin
$ specialtool 
SAME:$ /opt/specialtool
$ sudo vim /etc/skel/.bashrc

vi ~/.bashrc 
> export MYVAR=TRUE
$ source ~/.bashrc

sudo cp /etc/skel/.bash* default_data/
sudo touch /etc/skel/README
```
## Configure user resource limits
## Manage user privileges
## Manage access to the root account
## Configure PAM

# Networking
## Configure netowrking and hostname resolution statically or dynamically 
## Configure network services to start automatically at reboot
## Start stop and check the status of network services 
## Implement packet filtering
## Statically route IP traffic
## Synchronize time using other network peers

# Service Configuration
## Configire a caching DNS server
## Maintain a DNS zone
## Configure email aliases
## Configure an IMAP and IMAPS service
## Configure SSH servers and clients
## Restrict access to the HTTP proxy server
## Configure an HTTP server
## Configure HTTP server log files
## Restrict access to a web page 
## Configure a database server
## Manage and configure containers 
## Manage and configure Vertual Machines

# Storage Management
## List create delete and modify physical storage partitions
## Configure and manage swap space
## Create and configure file systems
## Configure systems to mount file systems at or during boot 
## Evaluate and compare the basic file system feature and options
## Manage and configure LVM storage
## Create and configure excrypted storage 
## Create and manage RAID devices 
## Setup user and group disk quotes for filesystems



## Heading 2 link [Heading link](https://github.com/pandao/editor.md "Heading link")
## Headerdds (Underline)
