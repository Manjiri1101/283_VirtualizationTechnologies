# CMPE283 : Virtualization Technology
# Assignment 2 : Modifying instruction behavior in KVM

Student names: Manjiri Kadam, Pranjali Kotgire
University Name: San Jose State University

### Prerequisites
• You will need a machine capable of running Linux, with VMX or SVM virtualization features exposed.
You may be able to do this inside a VM, or maybe not, depending on your hardware and software
configuration. You should likely be using the environment you created for assignment 1.

#### The Assignment
Your assignment is to modify the CPUID emulation code in KVM to report back additional information
when a special CPUID “leaf function” is called.
• For CPUID leaf function %eax=0x4FFFFFFF:
◦ Return the total number of exits (all types) in %eax
◦ Return the high 32 bits of the total time spent processing all exits in %ebx
◦ Return the low 32 bits of the total time spent processing all exits in %ecx
▪ %ebx and %ecx return values are measured in processor cycles
At a high level, you will need to perform the following:
• Configure a Linux machine, either VM based or on real hardware. You may use any Linux
distribution you wish, but it must support the KVM hypervisor.
• Download and build the Linux kernel source code (see below)
• Modify the kernel code with the assignment functionality:
◦ Determine where to place the measurement code
◦ Create new CPUID leaf 0x4FFFFFFF
▪ Report back information as described above
• Create (or otherwise locate) a user-mode program that performs various CPUID instructions
required to test your assignment
• Verify proper output

## How we built the kernel:
Please follow the steps:

1)We followed the steps to install the VM, then Ubuntu on our Windows / Mac PC. Installed ISO - Ubuntu 18.5, allocated disk space of 250 GB.
2) We have cloned the Linux github repository, using following command;
  `git clone https://github.com/torvalds/linux.git `
3) We followed the insructions given in the Assignment pdf to build kernel.

 Checked the Linux Version (old):
 `uname -a`
 O/P:
 
 4) Installed the dependency;
 `sudo apt-get install build-essential kernel-package fakeroot libncurses5-dev libssl-dev ccache bison flex libelf-dev`
 5) Noted the kernel Version by using - `uname -r` which was: 
