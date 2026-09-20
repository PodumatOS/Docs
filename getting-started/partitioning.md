# Partitioning

Disk partitioning is the process of creating a partition table on a physical disk. The partition table describes which areas of the disk belong to which partition and what type each partition is.

Any device (for example, a disk or a partition) that contains a mountable filesystem is called a volume.

You can create either a single partition spanning the entire disk, or several partitions (it all depends on your needs).

## Why disk partitioning is needed

First, a single physical disk can be divided into several logical parts (partitions).
Second, without a partition table the operating system does not know where to look for files.
Third, disk partitioning is required to launch the graphical installation of the operating system onto a drive.

## Why it's needed in PodumatOS

- Files are stored on a partition with a filesystem (FAT32, ext2).
- A partition is created inside a partition table (MBR).
- A partition is formatted with a filesystem before use.

## About the partition table

There are two main partition table formats (MBR is used for now).

**MBR** appeared in 1983 together with IBM PC DOS 2.0. It is located in the first 512 bytes of the disk and consists of bootloader code (about 446 bytes), the partition table (64 bytes), and the signature (2 bytes).
The maximum disk size is about 2 TB. The maximum number of primary partitions is 4. It uses the CHS (Cylinder, Head, Sector) addressing scheme.

**GPT** was designed as part of the Unified Extensible Firmware Interface standard (known as UEFI). The first 512 bytes contain an MBR for compatibility with older systems. It contains the partition table header and an array of GUID entries (a partition table with unique identifiers).
The maximum disk size is practically unlimited, which is why it is starting to replace MBR. It will be implemented in PodumatOS soon.

## Partitioning process

Below is how to partition a disk in the PodumatOS operating system:

### Step 1: Create an empty partition table.

```bash
fdisk init
```
### Step 2: Create a partition.

```bash
fdisk create 0 FAT32 64
```
Where `0` is the partition number, `FAT32` is the partition type (FAT32, and soon EXT2 will also be available), and `64` is the size in megabytes.

### Step 3: Verify the partitions.

```bash
fdisk
```
Shows the list of partitions with their type, LBA, and size.

### Step 4: Format the partition.

```bash
format
```
Finds the first FAT32 partition and formats it. Without this, mounting will not work.

### Step 5: Mount It

```bash
mount C: 2048
```
Where `C:` is the drive letter, and `2048` is the LBA of the partition start.

### Step 6: Verify the partitions.

```bash
drives
```
Your partition should be displayed.

## Full command sequence

```bash
fdisk init
fdisk create 0 FAT32 64
fdisk
format
mount C: 2048
drives
```

## LBA (Logical Block Address)
The sector number on the disk. Sectors are numbered starting from 0.

- LBA 0 – the MBR.
- LBA 1–2047 – often free for alignment.
- LBA 2048 – the start of the first partition (standard).

**Alignment** means that the start of a partition must be aligned to a certain boundary.

The partitioning system and the filesystem will continue to be developed in **PodumatOS**. All new updates will be published in the repository.

