# About PodumatOS
**PodumatOS** is a hobby operating system for x86_64, written from scratch
in C++ and NASM. 

## Why PodumatOS was created
PodumatOS is an operating system where you configure everything yourself. 
For example, during installation you can remove any component from the system (such as Bluetooth) and enable a specific package system of your choice. 
This operating system also supports legacy components, with automatic fallback to legacy components (ATA PIO and PS/2).

## System philosophy
PodumatOS is built on the idea that you have full control over your OS. 
There is no telemetry in this operating system, and the code is completely open.
PodumatOS is distributed under the BSD-2-Clause license, so you can freely use, modify, and release various distributions based on the PodumatOS kernel. 
The kernel was written from scratch using various examples and the OSDev wiki.

## Who this operating system is for

It is designed for enthusiasts and developers interested in OSDev, students, and those who want complete freedom and maximum system customization.

## System status

PodumatOS is currently in alpha and under development.

## Terminology useful in OS development

| Term | Meaning |
|------|---------|
| **Operating System (OS)** | Software that manages hardware and provides services for programs. |
| **Kernel** | The core of an OS – manages memory, processes, and hardware. |
| **Driver** | Software that lets the OS talk to a specific piece of hardware. |
| **Bootloader** | Software that loads the OS kernel at startup. |
| **Framebuffer** | Memory region that the GPU reads to display an image. |
| **Filesystem** | A way to organize files on a disk (e.g., FAT32, ext2). |
| **Userspace** | Where normal programs run (ring 3). |
| **Kernel space** | Where the kernel and drivers run (ring 0). |
| **Interrupt** | A signal to the CPU that something needs attention. |
| **MMIO** | Memory-Mapped I/O – talking to hardware by reading/writing memory addresses. |
| **DMA** | Direct Memory Access – hardware reading/writing RAM without CPU. |
| **PCI** | A bus for connecting devices to the motherboard. |
| **AHCI** | Interface for SATA disks. |
| **ATA PIO** | Older interface for disks (before AHCI). |
| **MBR** | Master Boot Record – a partition table format. |
| **FAT32** | A simple filesystem, widely supported. |
| **ext2** | A filesystem used by Linux. |
| **USB** | Universal Serial Bus – a standard for connecting devices. |
| **EHCI** | USB 2.0 host controller interface. |
| **xHCI** | USB 3.0 host controller interface. |
| **PS/2** | Older keyboard/mouse interface. |
| **HID** | Human Interface Device – keyboards, mice, etc. |
| **Limine** | The bootloader used by PodumatOS. |
| **HHDM** | Higher Half Direct Map – a memory layout provided by Limine. |
| **BSD-2-Clause** | The license of the PodumatOS source code. |
| **CC BY 4.0** | The license of this documentation. |
