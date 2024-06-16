---
title : "The System Preparation"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

#### CentOS Installation

1. The initial step is to have the compiler for GCC introduced:

```
sudo yum -y install gcc
```

2. Presently, the bundles to foster the piece are the following at the establishment level:

```
sudo yum -y install kernel-devel
```

3. All in all, the ulility of the make comes next for the establishment:

```
sudo yum -y install make
```

#### Ubuntu Installation

1. The compiler for GCC is the first in the establishment line:

```
sudo apt-get install GCC
```

2. Then, at that point, the bundles for part advancement come straightaway:
 
```
sudo apt-get install kernel-package
```

3. Then, at that point, the utility of the make establishment:

```
sudo apt-get install make
```

#### The kernel module

1. This is ``hello.c`` source code and full sample Makefile:

```
#include <linux/module.h>
#include <linux/kernel.h>
#include <linux/init.h>

static int __init hello_init(void)
{
    printk(KERN_INFO "Hello, World !!!\n");
    return 0;
}

static void __exit hello_exit(void)
{
    printk(KERN_INFO "Exiting ...\n");
}

module_init(hello_init);
module_exit(hello_exit);

MODULE_LICENSE("GPL");
MODULE_AUTHOR("Narendra Kangralkar.");
MODULE_DESCRIPTION("Hello world module.");
MODULE_VERSION("1.0");
```
![insmod](/images/2-Prerequiste/2/1.png)

2. Create file `Makefile`

```
obj-m += hello.o

all:
	$(MAKE) -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

clean:
	$(MAKE) -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean
```

3. Execute the following commands to compile and load the module:

```
make clean
make
sudo insmod hello.ko
```
![insmod](/images/2-Prerequiste/2/2.png)

4. If you still get the **"Invalid module format"** error, provide the output of dmesg so you can diagnose the cause of the error in more detail. Here's how to test `dmesg`:

```
dmesg | tail
```
![insmod](/images/2-Prerequiste/2/3.png)

#### How to identify the process’ PID

1. **Using ``ps`` Command:**

The ``ps`` command displays information about active processes. You can use it along with grep to find the PID of a specific process by its name.

```
ps aux | grep nginx
```

2. **Using ``pgrep`` Command:**

The ``pgrep`` command searches for processes by name and outputs their PIDs.

```
pgrep nginx
```

3. **Using ``pidof`` Command:**

The ``pidof`` command returns the PID of the process with the specified name.

```
pidof nginx
```

![insmod](/images/2-Prerequiste/2/4.png)

#### How to Manage Users and Groups as a Linux Administrator

1. User Management:
- Creating a new user named "fcj":

```
sudo useradd fcj
```

- Setting a password for the user "fcj":

```
sudo passwd fcj
```

- Deleting the user "fcj":

```
sudo userdel fcj
```

2. Directory and File Permissions:

- Changing the permissions of a file named "example.txt" to read-write for the owner:

```
chmod u+rw example.txt
```
- Changing the owner of a directory named "data" to user "john" and group "users":

```
chown fcj:users data
```

3. Managing Superuser or Root:

- Using sudo:
```
sudo command_name
```

- Granting sudo access to a user:
```
sudo visudo
```

- Add the following line to grant sudo access to the user "fcj" by sql

```sql

fcj   ALL=(ALL:ALL) ALL
```

4. File System Hierarchy:

- Understanding FHS: Exploring the root directory and its subdirectories:
```
ls /
```

- Understanding the purpose of key directories like **/bin, /etc, /home, etc**.

5. Linux File Systems:

- Formatting and Mounting File Systems: Creating a new ext4 file system on a disk partition:
```
sudo mkfs.ext4 /dev/sdb1
```
  - Mounting the file system to a directory named "/mnt/data":

```
sudo mount /dev/sdb1 /mnt/data
```
