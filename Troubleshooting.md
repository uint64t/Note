# Troubleshooting

## libvirt

### cannot force off windows vm 

**Error description: **

Error resetting domain: Timed out during operation: cannot acquire state change lock (held by monitor=remoteDispatchDomainReboot)

**Possible cause: **

There's a host connected to vm use rdp

**Solution:**

?

### cannot access vm use rdp via ip of macvtap in vm

**Error description:**

possible to connect to vm directly from intranet machine, but cannot when forward specific port to public using frp

**Possilble cause:**

?

**Possible solution:**

**Solution:**

?

## network 

### cannot connect to internet after creating a network bridge

**Error description**

I create a series config to configure a network bridge, but after restarting systems-networkd, the connection to internet suddenly break, but I remember I have configured it to connect to internet correctly once.

**Possilble cause**

the route of network is broken after create this bridge

**Possilble solution**

delete specific route rules 

**Solution**

?

## nvidia

### cannot sign in to Nvidia experience

**Error description**

Sign in page stuck in the popup window

#### Solution

run as administrator 

## arch

### can't boot into arch

**Error description**

can't auto boot into arch after install grub and init

#### Solution

install grub-bios (possible useful)

do mkinitcpio befor grub-mkconfig, it must report it found vmlinuz-linux and initramfs-linux.img

