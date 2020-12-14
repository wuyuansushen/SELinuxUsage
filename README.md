# SELinuxUsage

## 1.Install manage tool

```
dnf -y install policycoreutils-python-utils
```

## 2.Check SELinux status

Simple:
```
getenforce
```

Complex:
```
sestatus
```

## 3.Modify SELinux policy configuration

Temporary:
```
setenforce [ 0 | 1 ]
```

>Tip: 0=Permissive, 1=Enforcing

Permanent:
file `/etc/selinux/config`
```
SELINUX=enforcing
```

## 4.Change SELinux Port Type

>:warning:Following operation must be with SELinux On enviroment

List SELinux Port Type
```
semanage port -l
```

Add SELinux Port Type

```
semanage port -a -t <SELinuxPortType> -p [ tcp | udp ] [ PortNumber ]
```

Delete SELinux Port Type
```
semanage port -d -t <SELinuxPortType> -p [ tcp | udp ] [ PortNumber ]
```

## 5.Change SELinux File type

List SELinux File type
```
ls -aslZ <DirectoryPath>
```

Change SELinux File type with reference another file
```
chcon -R -v --reference=<ReferenceFile> <FilePath>
```

Change SELinux File Default context type
```
semanage fcontext -a -t <SELinuxFileType> "<DirectoryPath>(/.*)?"
```

Restore SELinux File type with default context
```
restorecon -R -v <FilePath>
```

## 6. (Advanced) Change SELinux Service type
Generate a local policy module to allow some access
