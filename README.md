# DNFStrap
Instant Fedora!

Do you like Fedora? Are all your friends using Arch Linux but you're afraid of them looking down on you for using a "Just Works" system?

Then you've come to the right place.

DNFStrap is a collection of scripts to bootstrap a minimal Fedora/Ultramarine chroot from scratch using DNF.

It also automatically sets up SELinux and other security features, and even networking! It even partitions your disk for you if you really want it to.

You don't even need Fedora to run it! DNFStrap runs on any Linux distribution that can run DNF, including Arch, Debian, and more!

As long as you have DNF installed, you can instantly bootstrap a bootable Fedora system anywhere, anytime, without using Red Hat's Anaconda installer at all.

This script is written entirely in Bash, and is designed to be run on a seperate live CD or USB drive.

# Usage
Simply clone this git repository to your local machine, and run the script.
```
git clone https://gitlab.ultramarine-linux.org/extras/dnfstrap.git && cd dnfstrap
```

To use the script, execute the `dnfstrap` script with the block device/mounted directory you want to use as the chroot and the base version of Fedora you want to use.
```
./dnfstrap -r 35 -d /dev/sda
```
You can also make it install extra packages with the `-i` flag, or use the `-p` flag to install packages from a file with a list of package names (one per line, can also be extra DNF arguments).
```
./dnfstrap -r 35 -d /dev/sda -i htop -i vim -p /path/to/packages.txt
```
By default, this script is meant to install Ultramarine Linux, but you can also use it to install Fedora by adding `-i fedora-release` to the command and removing the `ultramarine.repo` file in the repos directory.
