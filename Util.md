**usefull tutorial:** https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud

# Git

## About global settings

``` shell
# set global ignore rules
git config --global core.excludesfile <ignore_file>
# set global user about localhost
git config --global user.name <username>
git config --global user.email <email>
git config --global user.password <password>
# set git push without passwd
git config --global credential.helper store
# set proxy
git config --global http.proxy serverAddr:Port
# show global config
git config --global --list
```

## About tricks

``` shell
# remove file that had been added by git add
git rm -r --cached <path>
# remove commit history 
git reset --hard HEAD~1
```

# Tmux

## tmux command

```shell
# tmux source file
tmux source-file ~/.tmux.conf
```

