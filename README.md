# /etc/fstab: Static File System Information

## 🌟 Overview 🌟
The `/etc/fstab` file is a static file system configuration file used by the mount command to automatically mount filesystems at boot time and other relevant system startup points. It contains entries for each filesystem that needs to be mounted and specifies the mount point, filesystem type, mount options, and other parameters.

## 🛠️ Structure 🛠️
Each line in `/etc/fstab` represents a separate filesystem entry and follows a specific format:

```plaintext
<file system> <mount point> <type> <options> <dump> <pass>
```

- **<file system>**: Specifies the block special device or remote filesystem to be mounted.
- **<mount point>**: Specifies the directory where the filesystem is to be mounted.
- **<type>**: Specifies the filesystem type (e.g., ext4, vfat, ntfs).
- **<options>**: Specifies mount options for the filesystem, separated by commas.
- **<dump>**: Used by the dump command to determine which filesystems need to be dumped.
- **<pass>**: Used by the fsck command to determine the order in which filesystem checks are done at boot time.

## 🌐 Linux File Systems 🌐

### 🟢 Boot 🟢
- **/boot/efi**  
  ```plaintext
  UUID=938A-C3D9  /boot/efi  vfat  defaults  0 1
  ```

### 🔵 Swap 🔵
- **Swap Partition**  
  ```plaintext
  UUID=754410bd-1c33-4883-8e8b-4a4bf6b801cf  swap  swap  defaults  0 0
  ```

### ⚫ Root ⚫
- **/ (Root)**  
  ```plaintext
  UUID=bd34e248-d688-4f2b-9f74-8e18c3f76120  /  btrfs  subvol=/@,defaults,noatime,autodefrag,discard,compress=lzo  0 2
  ```
- **/swap (Swap Subvolume)**  
  ```plaintext
  UUID=bd34e248-d688-4f2b-9f74-8e18c3f76120  /swap  btrfs  subvol=/@swap,defaults  0 0
  ```

### 🟠 Home 🟠
- **/home**  
  ```plaintext
  UUID=10e18865-b502-4fae-af32-c781ce2fdb8a  /home  btrfs  defaults,noatime,autodefrag,discard,compress=lzo  0 3
  ```

### 🟣 Others 🟣
- **/swap/swapfile (Additional Swap File)**  
  ```plaintext
  /swap/swapfile  swap  swap  defaults  0 0
  ```
- **/tmp (Temporary Filesystem)**  
  ```plaintext
  tmpfs  /tmp  tmpfs  defaults,noatime,mode=1777  0 0
  ```

## 🌐 Windows File Systems 🌐

### 🟥 nvme0n1p1 (part_1) 🟥
- **/media/us/part_1**  
  ```plaintext
  UUID=01DABBD7BAD624D0  /media/us/part_1  ntfs-3g  defaults,uid=1000,gid=1000,permissions  0 0
  ```

### 🟨 nvme0n1p2 (part_2) 🟨
- **/media/us/part_2**  
  ```plaintext
  UUID=01DABBD7A2ACB040  /media/us/part_2  ntfs-3g  defaults,uid=1000,gid=1000,permissions  0 0
  ```

### 🟧 nvme0n1p3 (part_3) 🟧
- **/media/us/part_3**  
  ```plaintext
  UUID=01DABBD7A1D1B990  /media/us/part_3  ntfs-3g  defaults,uid=1000,gid=1000,permissions  0 0
  ```

### 🟩 nvme0n1p4 (part_4) 🟩
- **/media/us/part_4**  
  ```plaintext
  UUID=01DA42E05D331FB0  /media/us/part_4  ntfs-3g  defaults,uid=1000,gid=1000,permissions  0 0
  ```

### 🟦 nvme0n1p5 (part_5) 🟦
- **/media/us/part_5**  
  ```plaintext
  UUID=6DA288B407F175FE  /media/us/part_5  ntfs-3g  defaults,uid=1000,gid=1000,permissions  0 0
  ```

## 📝 Additional Notes 📝
- Entries prefixed with `#` are comments and are not parsed by the system.
- The `blkid` command can be used to retrieve UUIDs for devices.
- Care must be taken when modifying this file to avoid system instability or failure.

For detailed information, see the `fstab(5)` manual page.
