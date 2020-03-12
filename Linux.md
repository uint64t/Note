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

## Packages

``` shell
## for Ubuntu
# install oh-my-zsh
apt install zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
apt install autojump
git clone https://github.com/zsh-users/zsh-autosuggestions ./$ZSH/custom/plugins/
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ./$ZSH/custom/plugins/
git clone https://github.com/Powerlevel9k/powerlevel9k ./$ZSH/custom/themes/
```

## Command 

``` shell
# copy public key to server
cat <key_path> | ssh -p 8530 [-i <exist_key_path>] username@ip_or_domain "cat >> ~/.ssh/authorized_keys"

# kill all processes that occupy VRAM but idle
ps -aux | grep <script_name> | grep -v grep | awk '{print $2}' | xargs kill

```

