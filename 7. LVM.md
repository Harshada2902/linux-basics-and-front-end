
## LVM
##### Introduction :
-LVM stands for Logical Volume Management.

- LVM creates a layer of abstraction over physical storage, allowing you to create logical storage volumes.

 With LVM in place, you are not bothered with physical disk sizes because the hardware storage is hidden from the software 
so it can be resized and moved without stopping applications . You can think of LVM as dynamic partitions.

##  
1.Physical Volume (PV): it is a whole disk or a partition of a disk

2.Volume Group (VG): corresponds to one or more PV

3.Logical Volume (LV): represents a portion of a VG. A LV can only belong to one VG. It’s on a LV that we can create a file system.

##### Create Physical Volume:
-Physical volume is the actual storage device that will be used in the LVM configuration. 
-You can use 'pvcreate' command to create the physical volume
-'pvdisplay' command to display the physical volume

##### Create Volume Group:
-Physical volumes are combined into volume groups (VGs). It creates a pool of disk space out of which logical volumes can be allocated.

-The disk space available for allocation in Volume Group is divided into units of a fixed-size .

-vgcreate vgname[pv] => to create a volume group
=>vgcreate vg-1 /dev/sdb /dev/sdc

 Volume group "vg-1" successfully created
-vgdisplay => to display the volume group

##### Create Logical Volume:
-A volume group is divided up into logical volumes. 
-So if you have created vg-1 earlier then you can create logical volumes from that VG.
-The amount of space you want to allocate depends on your requirement.

-lvcreate -n name -L[size] name =>to create a logical volume.
-lvdisplay => to display the logical volume.



1. List partitions=> Parted -l
2. Label a partition=> parted / dev /vdb mklabel msdos => parted -l 
3. Use mkpart to make a partition=> parted /dev /vdb => mkpart=> primary=> xfs=> 2048s=> x%=>  flag set ->set1=> LVM=> on=> p
4. Let the partition be created/settled=>quit first then=> pvcreate/dev/vdb1/dev/vdc1 =>vgcreate servervg/dev/vdb1/dev/vdc1=> vgdisplay=> 
lvcreate -n serverlv -L	10vg servervg =>lvdisplay=> vgdisplay
5. Attach the file system to the partition=> mkfs. xFs /dev/servervg/serverlv
6. Create a mount point directory=> df-h => mkdir / archive
7. Add entry in fstab=> cat/etc/fstab=> vi/etc/fstab=> lsblk -- fs / dev / vdb
8. Systemctl daemon-reload=> system etl daemon -reload 
9. Mount the partition on the directory=> mount/archieve=>  df-h 
                  
    

         
            

    
