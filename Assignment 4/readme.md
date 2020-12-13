
# CMPE283 : Virtualization Technology
# Assignment 4 : Nested Paging vs. Shadow Paging

#### Student names: Manjiri Kadam, Pranjali Kotgire
#### University Name: San Jose State University

### Prerequisites
• You will need a machine capable of running Linux, with VMX or SVM virtualization features exposed.
You may be able to do this inside a VM, or maybe not, depending on your hardware and software
configuration. You should likely be using the environment you created for assignment 3.

## Question 1:
### Assignment Contribution of each Team Member
#### Pranjali Kotgire
1. Studied nested and shadow paging
2. Worked on kvm-intel module
3. Created Document
4. Examine number of exits with ept and without ept


#### Manjiri Kadam
1. Studied nested and shadow paging
2. Worked on kvm module
3. Updated Document
4. Examine number of exits with ept and without ept

## Question:2
## Include a sample of your print of exit count output from dmesg from “with ept” and “without ept”.

1. Before removing the modules, the output of total exits after running the VM on assignment 3.

2.  Removed the kernels i.e. kvm-intel.ko and kvm.ko 
![](https://github.com/Manjiri1101/283_VirtualizationTechnologies/blob/master/Assignment2/vmx.png)

3.  Insert the kernels with ept=0 

4. After rebooting, check the total exits:



