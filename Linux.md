## information file

### Check Linux kernel version

``` shell
# Check Linux kernel version
# e.g. Linux version 3.2.0-23-generic-pae
cat /proc/version
uname -a
uname -r
```

### Check Linux system version

``` shell
# Check Linux system version
# e.g. Ubuntu 12.04 LTS
# NOTE:	some system didn't install lsb-release by default
# 			Centos can install with $ yum provides lsb-release
#				$ sudo yum install -y redhat-lsb-core
cat /etc/issue
cat /etc/lsb-release
lsb-release -a
```

### Check Hardware Status

``` shell
# Check CPU info
lscpu	
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

# install p7zip, used for 7z file
sudo apt install p7zip-full p7zip-rar

# Display images in the command line
sudo apt-get install catimg
```

Package **catimg** rendering:

![image-20200510142642030](https://tva1.sinaimg.cn/large/007S8ZIlgy1genc6itgx6j31dp0u01hv.jpg)

## Command 

``` shell
## Multiline comment
# Note: This type of redirection instructs the shell to read input from the current 
# source until a line containing only word (with no trailing blanks) is seen.
:<<word
	"Content be commented"
word

## Extract substring
# Delete all characters before the last '/' searched from the left to right of 'var', 
# and return the right content of the last '/'(excluded the '/')
${var##*/}
# Delete all characters after the last of '/' searched from the right to left of 'var',
# and return the left content of the last '/'(excluded the '/')
${var%%/*}
# Function table
# | Function | searched direction    | the first one | the last one |
# | Search   | From left to right    | # 						 | ## 					|
# | Search   | From right to left    | % 						 | %%						|
# | Delete   | in the left of #, ##  |							 |							|
# | Delete   | in the right of %, %% |							 |							|

## copy public key to server
cat <key_path> | ssh -p 8530 [-i <exist_key_path>] username@ip_or_domain "cat >> ~/.ssh/authorized_keys"

## kill all processes that occupy VRAM but idle
ps -aux | grep <script_name> | grep -v grep | awk '{print $2}' | xargs kill

## Get full path of a file 
echo $(cd $(dirname "$1") && pwd -P)/$(basename "$1")

## Iterate over a list of files with spaces
find . -iname "foo*" | while read f
do
    # ... loop body
done

```

**Link**: 

1. Multiline comment: https://stackoverflow.com/questions/2500436/how-does-cat-eof-work-in-bash
2. Extract substring: https://blog.csdn.net/ljianhui/java/article/details/43128465
3. Get full path of a file: https://stackoverflow.com/questions/5265702/how-to-get-full-path-of-a-file
4. Iterate over a list of files with spaces: https://stackoverflow.com/questions/7039130/iterate-over-a-list-of-files-with-spaces
5. 

### Extend Primary partition, using fdisk

```shell
# Note: If there's an error <GPT PMBR size mismatch > when using <fdisk -l>, then you should first to correct GPT table and GPT PMBR
sudo parted -l
# or
sudo parted /dev/sda unit s print
# or 
sudo gdisk -l /dev/sda

# delete old partition, and create a new one 
fdisk <device name>
>>> d	# delete the old one
>>> n # create a new one
>>> w

# resize filesystem 
resize2fs <device name>
```

