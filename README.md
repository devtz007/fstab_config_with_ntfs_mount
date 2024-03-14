<p>
  <strong>File System Table (/etc/fstab) Documentation</strong>
  <br>
  <br>
  <strong>Overview</strong><br>
  The /etc/fstab file is a static file system configuration file used by the mount command to automatically mount filesystems at boot time and other relevant system startup points. It contains entries for each filesystem that needs to be mounted and specifies the mount point, filesystem type, mount options, and other parameters.
  <br>
  <br>
  <strong>Structure</strong><br>
  Each line in /etc/fstab represents a separate filesystem entry and follows a specific format:
  <br>
  &lt;file system&gt; &lt;mount point&gt; &lt;type&gt; &lt;options&gt; &lt;dump&gt; &lt;pass&gt;<br>
  - &lt;file system&gt;: Specifies the block special device or remote filesystem to be mounted.<br>
  - &lt;mount point&gt;: Specifies the directory where the filesystem is to be mounted.<br>
  - &lt;type&gt;: Specifies the filesystem type (e.g., ext4, vfat, ntfs).<br>
  - &lt;options&gt;: Specifies mount options for the filesystem, separated by commas.<br>
  - &lt;dump&gt;: Used by the dump command to determine which filesystems need to be dumped.<br>
  - &lt;pass&gt;: Used by the fsck command to determine the order in which filesystem checks are done at boot time.
  <br>
  <br>
  <strong>Entries</strong><br>
  <strong>Boot and Others</strong><br>
  1. Swap Partition<br>
  - UUID: ad5ae035-0707-434a-94b2-716d661132ba<br>
  - Mount Point: none<br>
  - Type: swap<br>
  - Options: sw<br>
  - Dump: 0<br>
  - Pass: 0<br>
  2. Linux Bootloader Partition<br>
  - UUID: e9f4c97c-6ecc-45a7-8483-4552d32a7e53<br>
  - Mount Point: /boot<br>
  - Type: ext4<br>
  - Options: defaults<br>
  - Dump: 0<br>
  - Pass: 2<br>
  3. EFI System Partition<br>
  - UUID: 4C85-81AF<br>
  - Mount Point: /boot/efi<br>
  - Type: vfat<br>
  - Options: defaults<br>
  - Dump: 0<br>
  - Pass: 2<br>
  <strong>Disk 1</strong><br>
  4. Root Partition<br>
  - UUID: a72a6508-7ada-49d1-b823-2b14574772ba<br>
  - Mount Point: /<br>
  - Type: ext4<br>
  - Options: errors=remount-ro<br>
  - Dump: 0<br>
  - Pass: 1<br>
  <strong>Disk 2</strong><br>
  5. NTFS Partition 1<br>
  - UUID: 78FCDCC9FCDC82B4<br>
  - Mount Point: /media/us/part_1<br>
  - Type: ntfs<br>
  - Options: defaults,uid=1000,gid=1000,permissions<br>
  - Dump: 0<br>
  - Pass: 0<br>
  6. NTFS Partition 3<br>
  - UUID: 01DA42DDE5F97EF0<br>
  - Mount Point: /media/us/part_3<br>
  - Type: ntfs<br>
  - Options: defaults,uid=1000,gid=1000,permissions<br>
  - Dump: 0<br>
  - Pass: 0<br>
  7. NTFS Partition 5<br>
  - UUID: 6DA288B407F175FE<br>
  - Mount Point: /media/us/part_5<br>
  - Type: ntfs<br>
  - Options: defaults,uid=1000,gid=1000,permissions<br>
  - Dump: 0<br>
  - Pass: 0<br>
  <br>
  <strong>Additional Notes</strong><br>
  - Entries prefixed with # are comments and are not parsed by the system.<br>
  - The blkid command can be used to retrieve UUIDs for devices.<br>
  - Care must be taken when modifying this file to avoid system instability or failure.<br>
</p>
