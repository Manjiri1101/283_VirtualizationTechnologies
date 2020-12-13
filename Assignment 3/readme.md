# CMPE283 : Virtualization Technology
# Assignment 3 : Instrumentation via hypercall


#### Student names: Manjiri Kadam, Pranjali Kotgire
#### University Name: San Jose State University

### Prerequisites
• You will need a machine capable of running Linux, with VMX or SVM virtualization features exposed.
You may be able to do this inside a VM, or maybe not, depending on your hardware and software
configuration. You should likely be using the environment you created for assignment 2.

## Question 1:
### Assignment Contribution of each Team Member
#### Pranjali Kotgire
1. Completed the code for CPUID leaf node %eax = 0x4FFFFFFC part.
#### Manjiri Kadam
1. Completed the code for CPUID leaf node %eax = 0x4FFFFFFE part.

## Question 2:
### Steps Performed For Assignment:
1.To calculate the total time spent processing all exits and the time spent processing the exit number for the particular case, we made changes in vmx.c file and cpuid.c file.

2.Then compile and build the modules using following commands:
make -j 4 && make -j 4 modules

3.Install the modules using below commands:
make modules_install && make install 

4.Install cpuid package in the virt manager:
sudo apt-get install cpuid

5.Check the total exit time in the virt manager

