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

Permanent:
file `/etc/selinux/config`
```
SELINUX=enforcing
```
