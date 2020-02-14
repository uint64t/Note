## information file

``` shell
# Check Linux kernel version
# e.g. Linux version 3.2.0-23-generic-pae
cat /proc/version
uname -a
uname -r
# Check Linux system version
# e.g. Ubuntu 12.04 LTS
# NOTE:	some system didn't install lsb-release by default
# 			Centos can install with $ yum provides lsb-release
#				$ sudo yum install -y redhat-lsb-core
cat /etc/issue
cat /etc/lsb-release
lsb-release -a
```

