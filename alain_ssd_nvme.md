* ## SSD nvme
* ### Alain Does
* #### Slackware linux

Alright, you just got that fast **NVMe SSD**, or even a couple…
You hope this drive, the _size of a pack of chewing gum_, will feed your need for speed.
So, you install it in your system… and notice that your system is noticably more responsive; but there’s something that makes you feel as though you might have missed something. What is it?

Well, for starters, most likely, the one thing most people tend to overlook, is the _filesystem_ they choose to format their new NVMe SSD with. Two of the most popular filesystems on Linux are “The Fourth Extended Filesystem” or as it is also known: “ext4”, and XFS, which is a 64-bit journaling file system created by Silicon Graphics, Inc

**EXT4** and _XFS_ are robust, journalling filesystems, and very well known and supported in the Linux world. They are also given as options for formatting hard drives, during installation of the various Linux distributions. But what is not as well known, is that EXT4 and XFS, like most other filesystems, were _never_ intended to be used on anything other than spinning hard drives.
There was no NAND flash-based media when they were developed.

Granted, it works fine, can be grown or shrunk, depending on the needs of the user or system administrator. Why then, you ask, did I even write this tutorial?

## I’ll tell you.

SSDs and NVMe PCIe drives, are flash-based; and do things quite a bit differently than rotational hard drives. In short, the filesystem I’m about to suggest, **Flash Friendly Filesystem (F2FS)**, has been designed from the ground up, specifically NAND flash-based SSDs, by _Samsung_. Static binaries start up noticably faster on this filesystem. And in this tutorial, I will be using a pair of Samsung EVO PLUS 970 NVMe SSDs which offer sequential performance at read/write speeds of up to 3,500/3,300 MB/s.
And as a bonus, the 970 EVO Plus includes an AES 256-bit hardware-based encryption engine; a nice touch for those who like to encrypt their data.

Why two? Because my motherboard has two M.2 slots, while some have three or more; and because I prefer at least two drives in my setup. This means that in your case, one drive might get a Windows installation, and the other Linux, or a Virtual Machine (VM) if you’re into that sort of thing.

Personally, I advise installing 

* ‘/’ (root) on drive 1, and 
* ‘/home’ (user files) on drive 2.
Or maybe you’re a video editor, and the Operating System (OS) is on drive 1, and drive 2 for your video editing and rendering software, etc. Or perhaps you’re a gamer, and place the OS on drive 1, and your games on drive number 2.

The point is, when possible, place your OS on drive 1, and the programs you install yourself, on the second drive. If you like, you could also just partition the drives, and have the OS on a partition of drive 1, and the programs on a partition on drive 2. This practice comes from the days of using relatively slow rotational hard drives, and having 2 or more drives available, which allowed you to interleave commands between the drives, and as a result, you end up not noticing any slowdowns in your perceived performance of the sytem.

Eventhough NVMe drives are _**way faster**_ than rotational drives, it’s still more efficient to separate large programs from the OS, eventhough some might say it’s not really necesarry, because the drives are so fast with a lot of throughput. It all depends on how you will be using the system.
Anyway, let’s get to the meat of this tutorial.
**F2FS stands for “Flash Friendly File System”, and was developed at Samsung Electronics Co., Ltd.**
And F2FS is also a filesystem designed to make the most of the performance capabilities of modern NAND flash-based devices. It was designed from the ground up, for that purpose.

While it is possible to use it on rotational hard drives, it would defeat the purpose; as you would not allow the filesystem to show you what it can do. It really should be used on NAND flash-based drives.
My personal layout I will describe below.

First the hardware specifications:

CPU Intel i9-9900k
MOTHERBOARD Asus TUF-Z390 PLUS GAMING
RAM 32GB DDR4

NVMe SSDs 2x Samsung 970 EVO PLUS 250GB

SATA SSDs 2x Samsung 860 EVO 1TB

SATA HDD 1x Western Digital 3TB 5400rpm

Linux OS Slackware -current 64 bit (August 30, 2019)

Since I desired to get the most user perceived speed out of the system, I used a combination of filesystems for the sytem, temp, and home partitions.
Like this:

* **Swap** is the first partition, and also the smallest, at 8GB.
* The OS root partition (**/**) at 32GB, is formatted with _**F2FS**_ (programs start fastest with F2FS)
* The temp partition (**/tmp**) at 40GB, is formatted with _EXT4_ (fastest when compiling software)
* The user files partition (**/home**) at 150GB, is formatted with _XFS_ (speedy for large and random files)

Here is a link with a speed test comparison between BTRFS, EXT, F2FS, XFS, on Linux:
https://www.phoronix.com/scan.php?pa...esystems&num=1

Now, one last thing, the drive space is setup under LVM (Logical Volume Management)
This makes it much simpler to shrink and or expand partition sizes, on the fly.
I created the following:

1. One Physical Volume (PV)
2. One Volume Group (VG)
3. Three Logical Volumes (LVs)

So far this is fairly straightforward.
I forgot to mention, that the other NVMe SSD was used for a Windows 10 installation, *before* I started with the install of Slackware Linux. This _prevents_ Windows from overwriting the bootloader.

Now, for those unfamiliar with creating an LVM setup, I'll give generic instructions, which should work on most Linux systems. Some of the instructions are lifted from alien Bob's slackware LVM. Read all the instructions before you begin. Let's go.

To create a new Logical Volume (LV), this has to happen before you run the part of the installer, where you actually install the OS. Start by creating the partition where you will place the LVM with fdisk for BIOS, or gdisk for GPT disks. After creating the partition, then change the type to "8e", which is Linux LVM. Reboot the system, and continue with setting up the LVM.

Now I will leave the partition sizes up to you, but in this example, I will be dividing a 250GB SSD, over 2 partitions; swap, and the rest of the space for system install.
Start as follows:

1. **pvcreate** /dev/nvme0n1p2 (<-- the second partiton after swap)

2. **vgcreate** slackware /dev/nvme0n1p2 (<-- slackware is the name I chose, can be anything)

3. **lvcreate -L** 32GB -n root slackware

4. **lvcreate -L** 40GB -n temp slackware

5. *lvcreate -l* 100%FREE -n home slackware (this command uses all the remaining space for home)

Now you can continue with the OS installation.

Make sure you choose "/dev/slackware/root" as the "/" partition, when asked where to install to; and format it with F2FS.
Then make sure you choose "/dev/slackware/temp" to mount as the "/tmp" partition, and choose to format it with EXT4. And lastly, choose "/dev/slackware/home" to mount as the "/home" partition, and format it with XFS.

When the installer finishes, it will ask you to reboot. But select "no" and go with the option to let it drop you into a command prompt.
To boot this setup, you need to add the F2FS modules to your initrd, if using LILO, and install the F2FS tools in your OS, before you reboot.
Now, chroot into the installed OS, by typing: chroot /mnt (<-- Slackware specific instructions YMMV)

Here's the command to create the initrd for kernel version 4.19.69 with modules for LVM and F2FS:
(is a single line)
mkinitrd -c -k vmlinuz-generic-4.19.69 -f f2fs -r /dev/slackware/root -m crc32:libcrc32c:crc32c_generic:crc32c-intel:crc32-pclmul:f2fs

For a system using LILO, edit the lilo.conf file, so lilo uses the initrd, and add the following:
image = /boot/vmlinuz-generic-4.19.69
initrd = /boot/initrd.gz
root = /dev/slackware/root
label = linux
read-only

Run /sbin/lilo when you are done editing lilo.conf.

If using GRUB, after installing the F2FS tools, you need to make sure the LVM modules load before the rest of the system.
Edit /etc/default/grub, find the following line:
GRUB_PRELOAD_MODULES="... " (<-- there might be other modules already there)

And add the required modules between the quotation marks at the end.
Like so:

GRUB_PRELOAD_MODULES="... lvm f2fs"

Then run update-grub, wait for it to complete, and you should be set.
If at this point you reboot, and you can boot into your shiny new system without error, congratulations.
You are done. 

For suggestions on improving this tutorial, please email to:
wisesoniam@gmail.com
or simply reply to this thread

=========================================================================
DISCLAIMER:

If your computer explodes, any part of it gets damaged, you lose data, or Earth is destroyed as a result of you following these instructions... I am not responsible for anything other than providing you with the instructions on how to setup a system, with user-perceivable increased speed. Understand this before you go through with it.
Last edited by WiseSon; Today at 05:36 PM. Reason: typos, spacing
