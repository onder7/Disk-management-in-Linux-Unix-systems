# Disk Management and Essential Commands in Linux/Unix Systems

Disk management in Linux and Unix systems is one of the most fundamental responsibilities of system administrators. In this article, we will examine in detail the basic commands used in disk management and their purposes.

## 1. Disk Usage Monitoring Commands

### df (Disk Free)
The `df` command shows the usage status of file systems.
- `df -h`: Shows in human-readable format (GB, MB)
- `df -i`: Shows inode usage
- `df -T`: Shows filesystem type
- `df -l`: Shows only local filesystems

### du (Disk Usage)
The `du` command shows disk usage of directories and files.
- `du -h`: Shows in human-readable format
- `du -s`: Shows only the total size
- `du -a`: Shows all files
- `du -c`: Shows the grand total at the end

## 2. Disk Partitioning Commands

### fdisk
Classic disk partitioning tool:
- `fdisk -l`: Lists all disks and their partitions
- `fdisk /dev/sda`: Opens specified disk for partitioning

### parted
Modern disk partitioning tool:
- `parted -l`: Lists all disks and their partitions
- `parted /dev/sda print`: Shows partitions of a specific disk
- `parted /dev/sda mkpart`: Creates new partition

### gparted
Graphical disk partitioning tool:
- `gparted`: Launches the graphical interface

## 3. Filesystem Management

### mkfs (Make Filesystem)
Creating filesystems:
- `mkfs.ext4 /dev/sda1`: Creates ext4 filesystem
- `mkfs.xfs /dev/sda2`: Creates XFS filesystem
- `mkfs.btrfs /dev/sda3`: Creates BTRFS filesystem

### mount/umount
Mounting and unmounting disk partitions:
- `mount /dev/sda1 /mnt`: Mounts the disk
- `umount /mnt`: Unmounts the disk
- `mount -a`: Mounts all disks in fstab

## 4. Disk Health and Performance

### smartctl
Checking disk health:
- `smartctl -a /dev/sda`: Shows detailed disk information
- `smartctl -H /dev/sda`: Shows disk health status

### iostat
Disk I/O statistics:
- `iostat -x 1`: Shows disk performance metrics every second
- `iostat -m`: Shows statistics in MB

### fio
Disk performance testing:
- `fio --filename=/dev/sda --direct=1 --rw=randread`: Random read test
- `fio --filename=/dev/sda --direct=1 --rw=randwrite`: Random write test

## 5. Disk Issues and Solutions

### fsck (Filesystem Check)
Filesystem check and repair:
- `fsck /dev/sda1`: Checks filesystem
- `fsck -f /dev/sda1`: Forces check
- `fsck -y /dev/sda1`: Automatically answers "yes" to all questions

### badblocks
Bad sector checking:
- `badblocks -v /dev/sda1`: Checks for bad sectors
- `badblocks -w /dev/sda1`: Checks with write test (destructive)

## 6. LVM (Logical Volume Management)

### pvs/vgs/lvs
Listing LVM components:
- `pvs`: Shows physical volumes
- `vgs`: Shows volume groups
- `lvs`: Shows logical volumes

### pvcreate/vgcreate/lvcreate
Creating LVM components:
- `pvcreate /dev/sda1`: Creates physical volume
- `vgcreate vg0 /dev/sda1`: Creates volume group
- `lvcreate -L 10G vg0`: Creates 10GB logical volume

## Best Practices

1. **Regular Monitoring**: Monitor disk usage regularly
2. **Backup**: Always backup before important disk operations
3. **Performance Optimization**: Regularly check disk I/O performance
4. **Automated Checks**: Automate disk health checks
5. **Documentation**: Document disk configurations

## Common Issues and Troubleshooting

1. **Disk Space Issues**
   - Regular cleanup of temporary files
   - Log rotation
   - Identifying large files and directories

2. **Performance Problems**
   - Monitoring I/O wait times
   - Checking for fragmentation
   - Optimizing disk scheduling

3. **Hardware Failures**
   - Regular SMART checks
   - Monitoring system logs
   - Implementing RAID when necessary

## Security Considerations

1. **Access Control**
   - Setting appropriate permissions
   - Managing mount options
   - Encrypting sensitive data

2. **Audit Trail**
   - Logging disk operations
   - Monitoring file system changes
   - Tracking user activities

## Conclusion

Disk management in Linux/Unix systems is critical for system stability and performance. Effective use of these commands and tools allows system administrators to quickly identify and resolve issues. Regular disk monitoring and maintenance increase system reliability and prevent data loss.

## Additional Resources

- Man pages for each command
- Online Linux documentation
- Community forums and support channels
- Professional training materials

Remember that proper disk management is essential for:
- System performance
- Data integrity
- Resource optimization
- System reliability
- Disaster recovery

Always stay updated with the latest tools and best practices in disk management to maintain an efficient and reliable system.
