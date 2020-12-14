
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
![](https://github.com/Manjiri1101/283_VirtualizationTechnologies/blob/master/Assignment%203/dmesg.png)

2. Removed the kernels i.e. kvm-intel.ko and kvm.ko 
![](https://github.com/Manjiri1101/283_VirtualizationTechnologies/blob/master/Assignment%204/screenshot-1.png)

![](https://github.com/Manjiri1101/283_VirtualizationTechnologies/blob/master/Assignment%204/screenshot-3.png)

3. Check if the kernals are removed properly
![](https://github.com/Manjiri1101/283_VirtualizationTechnologies/blob/master/Assignment%204/screenshot-2.png)

4.  Insert the kernels with ept=0 
![](https://github.com/Manjiri1101/283_VirtualizationTechnologies/blob/master/Assignment%204/screenshot-4.png)

4. After rebooting, check the total exits:
![](https://github.com/Manjiri1101/283_VirtualizationTechnologies/blob/master/Assignment%204/screenshot-5.png)

## Question:3
## What did you learn from the count of exits? Was the count what you expected? If not, why not?
* Exit count increased when running the kernel with ept=0. 
* This behavior is expected because after reloading the kernels i.e. kvm-intel.ko and kvm.ko with ept=0, it will induce the shadow paging behavior inside our environment setup. 
* Shadow paging will always execute more exits than nested paging.
* We expected more countof number of exits and as expected output is same.

## Question:4
## What changed between the two runs (ept vs no-ept)?
* We created a nested virtualized environment in assignment 3 by running a VM on top of our local Linux machine. 
* By inserting the modules with ept=0, we have induced the shadow paging behavior which results into greater number of VM Exits.
* With nested paging performance and speed of the VM was good.
* With shadow paging performance and speed of the VM was not that good as compared to Nested paging.




