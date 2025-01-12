# Introduction
- [[#KVM]] (Kernel-Based Virtual Machine)
- [[#QEMU]] (Quick Emulator)

## KVM
[Home Page](https://www.linux-kvm.org/page/Main_Page)
**KVM** is a **Linux kernel module**. It is a type 1 hypervisor that is a **full virtualization** solution for Linux on x86 hardware containing virtualization extensions (Intel VT or AMD-V). But what is full virtualization, you may ask? When a CPU is emulated (vCPU) by the hypervisor, the hypervisor has to translate the instructions meant for the vCPU to the physical CPU. As you can imagine this has a massive performance impact. To overcome this, modern processors support virtualization extensions, such as Intel VT-x and AMD-V. These technologies provide the ability for a slice of the physical CPU to be directly mapped to the vCPU. Therefore the instructions meant for the vCPU can be directly executed on the physical CPU slice.
![[KVM_ARCHITECTURE.png]]
## QEMU
[Home Page](https://www.qemu.org/)
**QEMU** is a userland type 2 (i.e runs upon a host OS) hypervisor for performing **hardware virtualization** (not to be confused with hardware-assisted virtualization), such as disk, network, VGA, PCI, USB, serial/parallel ports, etc. It is flexible in that it can emulate CPUs via dynamic binary translation (DBT) allowing code written for a given processor to be executed on another (i.e ARM on x86, or PPC on ARM). Though QEMU can run on its own and emulate all of the virtual machine’s resources, as all the emulation is performed in software it is extremely slow.


## Installation

```bash
sudo apt install qemu-kvm libvirt-clients libvirt-daemon-system bridge-utils virtinst -y
```

Post installation steps:
```bash
sudo adduser $USER libvirt
sudo adduser $USER kvm
```

