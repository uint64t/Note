## MacSettings

``` shell
## Set Launchpad dispaly icon number
# Set rows
defaults write com.apple.dock springboard-rows -int 7
# Set columns
defaults write com.apple.dock springboard-columns -int 8
# Restart Launchpad
defaults write com.apple.dock ResetLaunchPad -bool TRUE;killall Dock
```

## Make disk image

```shell
# list identifier of USB flash disk 
diskutil list
# erase disk
diskutil eraseDisk MS-DOS "WINDOWS10" MBR <disk identifier>
# open iso image
# copy image to disk
cp -rp /Volumes/VolumeName/* /Volumes/WINDOWS10/
```

## Commands

``` shell
## to check cpuinfo of mac
# this command show the vendor, model and freq of cpu
sysctl -n machdep.cpu.brand_string	
# this show the number of Processors of cpu
system_profiler | grep processor

## Disable I/O priority constraints
sudo sysctl debug.lowpri_throttle_enabled=0

## Show hiden file 
defaults write com.apple.finder AppleShowAllFiles -bool true
```

### Mark

p.s: This section is used to record tips from blog etc. The function of these tips are not verified.

```shell
# When you can't open app with info "This app has been damaged" in macOS Catalina, you can try:
sudo xattr -d com.apple.quarantine </Path/To/App.app>
```



## Folders

``` shell
# To show volume in dock
# in Finder <Control+shift+G>, then input
/Volume	
# then drag folder icon to dock
```



## Packages

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

