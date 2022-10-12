# Lab 2 Linux Filesystem Tree Layout
## 2.1
```shell
$ du --help
$ sudo du --max-depth=1 -hx /
```
## 2.2
````shell
$ cd /proc
$ ls -F
$ ls -F 4435
````

# Lab 3 Processes
## 3.1 
````shell
$ help ulimit

$ bash
$ ulimit -n
1024

$ ulimit -S -n
1024

$ ulimit -H -n
4096

$ ulimit -n hard
$ ulimit -n
4096

$ ulimit -n 2048
$ ulimit -n 
2048

$ ulimit -n 4096
bash: ulimit: open files: cannot modify limit: Operation not permitted

$ ulimit -n
2048
````

## 3.2
```shell
$ ipcs
$ ipcs -p
$ ps aux |grep -e 20573 -e 2048

```

# Lab 4 Signals

````shell
$ gcc -o signals signals.c
$ ./signals
````

# Lab 5 Git
````shell
git init
ls -l .git
git add file
git config user.name "name"
git config user.email "mail"
git diff
git commit -m "message"
git log
````

# Lab 6 RPM

## 6.1
````shell
$ rpm -qf /etc/logrotate.conf
$ rpm -qil logrotate
$ rpm -V logrotate

sudo rpm -e logrotate
````

## 6.2
````shell
$ cd /var/lib
$ sudo cp -a rpm rpm_BACKUP
$ sudo rpm --rebuilddb
$ ls -l rpm rpm_BACKUP
$ rpm -qa | tee /tmp/rpm-qa.output
$ ls -l rpm rpm_BACKUP
$ sudo rm -rf rpm_BACKUP
````

# Lab 7 DPKG
````shell
$dpkg -S logrotate.conf
$ dpkg -L logrotate
$ dpkg -V logrotate
$ sudo dpkg -r logrotate
````

# Lab 8 DNF and YUM
## 8.1
````shell
$ sudo dnf update && sudo dnf check-update && sudo dnf lis updates
$ sudo dnf update bash
$ sudo dnf list installed "kernel*"
$ sudo dnf list "kernel*"
$ sudo dnf install httpd-devel
````
## 8.2
````shell
$ sudo dnf search bash
$ sudo dnf list bash 
$ sudo dnf info bash
$ sudo dnf deplist bash
````
## 8.3
```shell
$ dnf grouplist
$ dnf groupinfo "Virtualization Host"
$ sudo dnf groupinstall "Virtualization Host"
$ sudo dnf groupremove "Virtualization Host"
```
## 8.5
````shell
$ touch /etc/yum.repos.d/webmin.repo
$ vim webmin.repo

[Webmin]
name=Webmin Distribution Neutral
baseurl=http://download.webmin.com/download/yum
mirrorlist=http://download.webmin.com/download/yum/mirrorlist
enabled=1
gpgcheck=0

$ sudo dnf install webmin
````

# Lab 9 Zypper
# 9.1
````shell
$ zypper list-updates
$ sudo zypper update bash
$ zypper repos
$ zypper search -i kernel
$ zypper search kernel
$ sudo zypper install apache2-devel
````
## 9.2
````shell
$ zypper search -d bash
$ zyper search bash
$ zypper info bash
$ zypper info --requires bash
$ sudo zypper remove --dry-run bash
````

# Lab 10 APT
## Lab 10.1
````shell
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get -u upgrade
$ apt-cache search "kernel"
$ apt-cache search -n "kernel"
$ apt-cache pkgnames "kernel"
$ dpkg --get-selections "*kernel*"
$ sudo apt-get install apache2-dev
````
## 10.2
````shell
$ apt-cache search bash 
$ apt-cache search -n bash
$ apt-cache show bash
$ apt-cache depends bash
$ apt-cache rdepends bash
````
## 10.3
````shell
$ apt-cache search metapackage
$ sudo apt-get install bacula-client
````
# Lab 11 System Monitoring
````shell
$ git clone git://kernel.ubuntu.com/cking/stress-ng.git
$ cd stress-ng
$ make
$ sudo make install

$ stress-ng --help
$ info stress-ng
$ stress-ng -c 8 -i 4 -m 6 -t 20s
$ stress-ng -m 4 -t 20s
````
# Lab 12 Processes
## 12.1
````shell
$ ps -ef
$ ps aux

$ ps -o pid,pri,ni,cmd

$ bash
$ nice -n 10 bash
$ ps -o pid,pri,ni,cmd

$ renice 15 -p 22171
$ ps -o pid,pri,ni,cmd

$ top
````
## 12.2
`````shell
$ dd if=/dev/urandom of=/dev/null &
$ ps -C dd -o pid,cmd, stat
$ fg
$ ^Z
$ ps -C dd -o pid,cmd,stat
$ jobs
$ fg
$ kill 25899
`````
# Lab 13 Memory monitoring and usage
`````shell
$ sudo /sbin/swapoff -a
$ sudo /sbin/swapon -a
$ stress-ng -m 12 -t 10s
`````
# Lab 14 I/O Monitoring and tuning
## 14.1
`````shell
$ binnie++ --help
$ time sudo bonnie++ -n 0 -u 0 -r 100 -f -b -d /mnt
$ bon_csv2html < bonnie++.out > bonnie++.html
$ bon_csv2txt < bonnie++.out > bonnie++.txt
`````
## 14.2
`````shell
$ tar zxvf fs_mark-3.3.tgz
$ cd fs_mark
$ make

$ sudo dnf install glibc-static
$ sudo zypper install glibc-devel-static
$ fs_mark -d /tmp -n 2500 -s 10240
$ iostat -x -d /dev/sda 2 10
`````
# Lab 15 I/O Sheduling 
???
````shell
$ sudo ./lab_iosched.sh [# reads/writes (NMAX)] [file size in MB (NMEGS)]
$ echo 3 > /proc/sys/vm/drop_caches
````