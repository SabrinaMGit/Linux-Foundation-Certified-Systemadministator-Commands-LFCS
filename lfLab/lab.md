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