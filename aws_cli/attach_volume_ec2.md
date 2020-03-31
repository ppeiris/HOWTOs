# Attach a volume to EC2
- attach the volume 
- list the block
```
$ lsblk
```
- check for the file system  
```
$ sudo file -s /dev/xvdf
/dev/xvdf: data
```
(: data mean there is no file system)
- Create a file system
```
$ mkfs -t ext4 /dev/xvdf

mke2fs 1.42.9 (28-Dec-2013)
Filesystem label=
OS type: Linux
Block size=4096 (log=2)
Fragment size=4096 (log=2)
Stride=0 blocks, Stripe width=0 blocks
3276800 inodes, 13107200 blocks
655360 blocks (5.00%) reserved for the super user
First data block=0
Maximum filesystem blocks=2162163712
400 block groups
32768 blocks per group, 32768 fragments per group
8192 inodes per group
Superblock backups stored on blocks:
	32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208,
	4096000, 7962624, 11239424

Allocating group tables: done
Writing inode tables: done
Creating journal (32768 blocks): done
Writing superblocks and filesystem accounting information: done
```

- Check the file system 
```
$ sudo file -s /dev/xvdf
/dev/xvdf: Linux rev 1.0 ext4 filesystem data, UUID=b0d84fa2-a9cf-4278-b79f-e1cdc70f944f (extents) (64bit) (large files) (huge files)
```

- We have to mount that storage to a directory 
```
$ mkdir /ftrml 
```

- mount the directory
```
$ sudo mount /dev/xvdf /ftrml/
```

- Check the mount
```
$ df -hT
Filesystem     Type      Size  Used Avail Use% Mounted on
devtmpfs       devtmpfs   15G     0   15G   0% /dev
tmpfs          tmpfs      15G     0   15G   0% /dev/shm
tmpfs          tmpfs      15G  436K   15G   1% /run
tmpfs          tmpfs      15G     0   15G   0% /sys/fs/cgroup
/dev/xvda1     xfs       8.0G  1.3G  6.8G  16% /
tmpfs          tmpfs     3.0G     0  3.0G   0% /run/user/1000
/dev/xvdf      ext4       50G   53M   47G   1% /ftrml
```

- Add this permenantly update the /etc/fstab (Add the following line)

```
/dev/xvdf /ftrml ext4 defaults,nofail, 0 0
```

- Run the following command to mount

```
$ mount -a
```

- Give ec2-user to EBS volume 
```
$ sudo chown ec2-user /ftrml
```







