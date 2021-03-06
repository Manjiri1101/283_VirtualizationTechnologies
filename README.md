# CMPE283 : Virtualization Technology 
#### Assignment 1: Discovering VMX Features
#### student names: Manjiri Kadam, Pranjali Kotgire
#### University Name: San Jose State University

## Prerequisites
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

#### Assignment Details:
This is group assignment done by pranjali kotgire and Manjiri Kadam. Pranjali has worked on installation and configuration of virtual Machine. And Manjiri has worked on compilation of linux source code, Tried,Tested commands which are feasible with ubantu.Both of us studied,discuss on same assignment and we studied Intel SDM provided by professor and listened to the lecture provided by professor on this assignment.
Purpose of this assignment is to create a linux kernal module which would then query diffrent MSR's to get to know about vartulization features available in particular CPU. Detail step-by-step description is as given below:

## 

As the prerequisite, I have created the git repo, and installed `VMWare workstation` on my Windows10 Machine. On top of that I configured the Ubuntu machine - ISO Ubuntu 18.04.5.
`root@ubuntu:/home/manjiri/CMPE283-1# uname -r
5.4.0-52-generic `

<img src="install-essential.png"/>
This is prerquisite to run "Make" in Ubuntu.


As per the instructions, I have created the cmpe283-1.c file, please check it out in my git folder. I have used the following commands to run ".mo" file.

`root@ubuntu:/home/manjiri/CMPE283-1# vi cmpe283-1.c`

`root@ubuntu:/home/manjiri/CMPE283-1# make`

`root@ubuntu:/home/manjiri/CMPE283-1# insmod ./cmpe283-1.ko`


<img src="to-run.png"/>

The output for the file is shown in below screenshot:

`root@ubuntu:/home/manjiri/CMPE283-1# dmesg`

<img src="output.png"/>


Thank You.

