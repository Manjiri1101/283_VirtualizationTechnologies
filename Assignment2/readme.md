# CMPE283 : Virtualization Technology
# Assignment 2 : Modifying instruction behavior in KVM

#### Student names: Manjiri Kadam, Pranjali Kotgire
#### University Name: San Jose State University

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
 <img src="unameold.png" />
 
4) Installed the dependency;
 `sudo apt-get install build-essential kernel-package fakeroot libncurses5-dev libssl-dev ccache bison flex libelf-dev`
 
5) Noted the kernel Version by using - `uname -r` which was: 

7) `cd linux`

8) `cp /boot/config-$(uname -r) ./.config ` Replace (uname -r) eg- ` cp /boot/config-5.4.0-52-generic ./.config `

9) ` sudo make oldconfig ` (and then just use the default for everything, don’t change anything – you can do this by holding down enter)

10) Runthe following instruction in "Linux" folder one by one:
`sudo  make` ,  `sudo make modules` , ` sudo make install`  and `sudo make modules_install` 
These steps might need 4-6 hours to complete for the first time.

11) Then reboot the Ubuntu machine:
` sudo reboot`

12) Verify that you are using the newer kernel (5.8, etc) after reboot: `uname -a`

<img src="updated kernel.png" />

**Note :After executing these priliminary steps, we can edit the code. After changing the code in KVM for the assignment, you can rebuild using the same “make” sequence of
commands above (and it should only take a few minutes, not several hours).

                                                   
                                                    
#### Updating the KVM:
Please run the following commands one by one (root user)
1) `kvm-ok`
<img src="kvm.png" />

2) `sudo apt install cpu-checker`

3) `egrep -c ‘lm’ /proc/cpuinfo`

4) `sudo apt-get install virt-manager`
<img src="virtmanager.png" />


