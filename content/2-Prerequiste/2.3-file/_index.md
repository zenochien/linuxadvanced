---
title : "The File System of Linux"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

The procedure of putting away documents on a hard plate is a record framework. Furthermore, Linux upholds a few kinds of record frameworks including:
- Special-purpose file systems: debugfs, tmpfs, sysfs, procfs, etc.
- Flash storage file systems: YAFFS, JFFS2, ubifs, etc.
- Conventional disk file systems: NTFS, JFS, Btrfs, XFS, ext4, ext3, ext2, etc. 

#### The hierarchy standard of the file system

1. / (Root Directory):

    The top-level directory in the filesystem hierarchy.
    All other directories and files are subdirectories or files within the root directory.
    Contains essential system files and directories required for booting and operating the system.

2. /bin (Binaries):

    Contains essential command binaries (executable programs) that are required for system boot and maintenance.
    Binaries stored here are typically essential for single-user mode or for repairing the system in case of failures.

3. /sbin (System Binaries):

    Similar to /bin, but contains essential system administration binaries (executables) that are intended for root user use only.
    Binaries in /sbin are typically used for system administration tasks such as mounting filesystems, managing hardware, and configuring network interfaces.

4. /etc (Configuration Files):

    Contains system-wide configuration files and directories.
    Configuration files for various system services, network settings, user management, and system startup scripts are typically stored here.

5. /usr (User):

    Contains user-related programs, libraries, documentation, and other non-essential system files.
    Divided into subdirectories such as /usr/bin, /usr/sbin, /usr/lib, /usr/include, /usr/share, etc., each serving a specific purpose.

6. /var (Variable):

    Contains variable files such as logs, spool files, temporary files, and other files that may change frequently during system operation.
    Subdirectories include /var/log, /var/spool, /var/tmp, /var/run, etc.

7. /home (Home):

    Contains home directories for regular users.
    Each user has their own subdirectory within /home where they can store personal files and configurations.

8. /tmp (Temporary):

    Stores temporary files created by various programs.
    Files in /tmp are typically deleted upon system reboot or at regular intervals by system utilities.

9. /dev (Device):

    Contains device files that represent physical and virtual devices attached to the system.
    Device files are used by the kernel and device drivers to communicate with hardware devices.

#### Linux Data Manipulation

- `wc`: Counts lines, words, and characters in input.
- `du`: Shows disk usage of files and directories.
- `df`: Reports file system disk space usage.

1. Search for a Pattern in a File: 
- Command: `grep`
- Search for lines containing the word "error" in a log file named error.log:

```
grep "error" hello.mod.o
```

2. Count the Number of Lines, Words, and Characters in a File:
- Command: `wc`
- Count the number of lines, words, and characters in a file named data.txt:

```
wc hello.o
```

3. Replace Text in a File:
- Command: `sed`
- Replace all occurrences of "old_word" with "new_word" in a file named file.txt:

```
sed -i 's/old_word/new_word/g' hello.c
```

4. Sort and Remove Duplicate Lines from a File:
- Commands: `sort`, `uniq`
- Sort the lines in a file named hello.mod.o and remove duplicate lines:

```
sort hello.mod.o | uniq
```

5. Calculate Disk Usage of Directories:
- Command: `du`
- Show disk usage of the current directory and its subdirectories in human-readable format:

```
du -h
```

7. Create an Archive of Files:
- Command: `tar`
- Create a tarball (archive.tar.gz) of all files in the documents directory:

```
tar -czvf archive.tar.gz documents
```

8. Extract Files from an Archive:
- Command: `tar`
- Extract files from a tarball (archive.tar.gz) into the current directory:

```
tar -xzvf archive.tar.gz
```

#### Creating from the Command-line a File for Tar, GZip

1. Creating a Directory and Files
- First, create a directory and some files to work with:

```
mkdir my_files
cd my_files
echo "Hello, World!" > file1.txt
echo "This is a test file." > file2.txt
echo "Linux is great!" > file3.txt
cd ..
```

2. Creating a Tar Archive
- Use the `tar` command to create an archive (.tar) of the directory my_files:

```
tar -cvf my_files.tar my_files/
```

- Options:
    - c: Create a new archive.
    - v: Verbose mode (lists files being archived).
    - f: Specify the filename of the archive.

3. Compressing the Tar Archive with Gzip
- Use the `gzip` command to compress the tar archive (.tar.gz):

```
gzip my_files.tar
```

4. Creating a Tar and Gzip Archive in One Step
- You can create and compress the tar archive in one step using the z option:

```
tar -czvf my_files.tar.gz my_files/
```

- Options:
    - c: Create a new archive.
    - z: Compress the archive with gzip.
    - v: Verbose mode.
    - f: Specify the filename of the archive.

5. Extracting a Tar Archive
- To extract the files from a .tar archive:

```
tar -xvf my_files.tar
```

- Options:
    - x: Extract files from the archive.
    - v: Verbose mode.
    - f: Specify the filename of the archive.

6. Extracting a Gzip Compressed Tar Archive
- To extract the files from a .tar.gz archive:

```
tar -xzvf my_files.tar.gz
```

- Options:
    - x: Extract files from the archive.
    - z: Decompress the archive with gzip.
    - v: Verbose mode.
    - f: Specify the filename of the archive.