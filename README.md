# CMPE283 : Virtualization Technology 
##Assignment 1: Discovering VMX Features

##Prerequisites
• You will need a machine capable of running Linux, with VMX virtualization features exposed. You
may be able to do this inside a VM, or maybe not, depending on your hardware and software
configuration.
• You will need at least one github account (create one at github.com if you don’t already have one)

## Assignment - 01
Your assignment is to create a Linux kernel module that will query various MSRs to determine
virtualization features available in your CPU. This module will report (via the system message log) the
features it discovers.
At a high level, you will need to perform the following:
• Configure a Linux machine, either VM based or on real hardware. You may use any Linux
distribution you wish.
• Download and build the Linux kernel source code
• Create a new kernel module with the assignment functionality
• Load (insert) the new module
• Verify proper output in the system message log

## 

As the prerequisite, I have created the git repo, and installed `VMWare workstation` on my Windows10 Machine. On top of that I configured the Ubuntu machine - ISO Ubuntu 18.04.5.
`root@ubuntu:/home/manjiri/CMPE283-1# uname -r
5.4.0-52-generic `

<img src=""><img/>

