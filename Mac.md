``` shell
# Set Launchpad dispaly icon number

# Set rows
defaults write com.apple.dock springboard-rows -int 7
# Set columns
defaults write com.apple.dock springboard-columns -int 8
# Restart Launchpad
defaults write com.apple.dock ResetLaunchPad -bool TRUE;killall Dock
```

``` shell
# To show volume in dock
cd /Volume	# in Finder
# then drag folder icon to dock
```



## necessary package

``` shell
# util-linux is located in 
# /usr/local/opt/util-linux/
# setsid is located in bin
brew install util-linux
brew install aria2
brew install tmux
brew tap v2ray/v2ray
brew install v2ray-core
brew install archey
brew install autojump
brew install powerlevel9k
brew cask install neteasemusic
brew cask install qbittorrent
brew cask install mpv
```

