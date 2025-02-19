# RASPBERRY PI SETUP

```bash
sudo apt-get update
sudo apt-get -y upgrade

# Essential dependencies
sudo apt-get install -y build-essential git cmake make ninja-build libtool libtool-bin autoconf automake pkg-config unzip gettext ca-certificates ntfs-3g

# Mount USB
lsusb
blkid
blkid /dev/**
sudo ls -l /dev/disk/by-uuid  # list connected storage by UUID
mkdir /mnt/ext1  # create directory to mount USB
sudo chmod 775 /mnt/ext1  # give permission to created directory
sudo mount -t ntfs-3g -o uid=$USER,gid=$USER /dev/sda1 /mnt/ext1  # manual mount USB
sudo cp /etc/fstab /etc/fstab.bak  # create fstab backup
sudo nvim /etc/fstab

```

## References

1. [Raspberry Pi Documentation](https://www.raspberrypi.com/documentation/)
2. [Raspberry Pi Imager download](https://www.raspberrypi.com/software/)
3. [Change SSH port](https://forums.raspberrypi.com/viewtopic.php?t=57697)
4. [How to install neovim on Raspberry Pi](https://luther.io/articles/how-to-install-neovim-on-raspberry-pi/)
5. [Repo for creating neovim deb using docker](https://github.com/arch-fan/neovim-raspberry)
