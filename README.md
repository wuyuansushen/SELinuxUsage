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
