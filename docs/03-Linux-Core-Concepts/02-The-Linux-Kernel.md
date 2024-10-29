# Linux Core Concepts

- Take me to the [Video Tutorial](https://kodekloud.com/topic/linux-kernel/)

In this section, we will take a look at the core concepts of a linux operating system.
- We will start with introduction to the linux kernel.
- We will then learn about the kernel space and user space.

## Linux Kernel

#### If you have worked with any operating system, you have run into the term kernel. 

- The Linux kernel is monolithic, this means that the kernel carrries out CPU scheduling, memory management and several operations by itselfs. 
- The Linux Kernel is also modular, which means it can extends its capabilities through the use of dynamically loaded kernel modules

  ![linux-kernel](../../images/linux-kernel.PNG)

#### To understand a kernel in simple terms, let us use an analogy of a **`College Library`**. Here the librarian is equal to Linux Kernel.

![library](../../images/library.PNG)

#### The Kernel is responsible for 4 major tasks

1. Memory Management
1. Process Management
1. Device Drivers
1. System calls and Security

Linux kernel is _**monolithic**_ and **_modular_**.

- **Monolithic:** all this major task is handled by kernel itself
- **Modular:** The Linux kernel being modular means it’s designed in a way that allows different parts, or modules, of the kernel to be loaded or unloaded dynamically, depending on what the system needs. It specifies following properties -

  1. **Dynamic Loading and Unloading:** Modules, such as drivers for different hardware (e.g., network cards, file systems), can be added or removed from the kernel at runtime using commands like `modprobe, insmod, and rmmod`. This avoids the need to recompile or reboot the kernel for every change or new functionality.

  2. **Reduced Memory Usage:** Only the necessary modules are loaded into memory, conserving resources. 

  3. **Easier Customization and Maintenance:** You can compile only the core kernel and add features as needed, which simplifies maintenance and updates. For example, if a new piece of hardware requires a different driver, you can add its module without modifying the whole kernel.

  4. **Enhanced Stability:** If a module crashes, it can be unloaded and reloaded without affecting the entire system, which contributes to better system stability.

## Linux Kernel Versions

#### let us know identify the ways to identify linux kernel versions

Use **`uname`** command to get the information about the kernel (by itself it doesn't provide much information except that the system uses the **`Linux`** Kernel.
```
$ uname
```

Use the **`uname -r`** or **`uname`** comamnd and option to print the kernel version
```
$ uname -r
$ uname -a
```
   ![kernel-versions](../../images/kernel-versions.PNG)

## Kernel and User Space

#### One of the important functions of the linux kernel is the **`Memory Management`** . We will now see how memory is seperated within the linux kernel

Memory is divded into two areas.
1. Kernel Space
   1. Kernel Code
   1. kernel Extensions
   1. Device Drivers
1. User Space
   1. C
   1. Java
   1. Python
   1. Ruby e.t.c
   1. Docker Containers

Kernel space can be compared with designated space for librarian who has access to books and other materials.
whereas the user space can be compared with the space where the students can read books and reference other materials. User space in memory contain all the external application and some pre-packaged utilities applications like graphical tools or another programming language. 

![memory-management](../../images/memory-management.PNG)

#### Let us know see how programs running in the `User Space` work

All user programs function by manipulating data that is stored in memory and on disk. User programs get access to data by making special request to the kernel called **`System Calls`**
- Examples include, allocating memory by using variables or opening a file. If we compare this with analogy like student(user-space) is requesting for books (hardware) to librarian(kernel space). librarian decide to accept the request or not.


  ![user-space](../../images/user-space.PNG)

- For example, opening a file such as the **`/etc/os-release`** to see the operating system installed, results in a **`system call`**

  ![user-space1](../../images/user-space1.PNG)


