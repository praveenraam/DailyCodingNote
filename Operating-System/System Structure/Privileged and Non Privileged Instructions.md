Article [Link](https://www.geeksforgeeks.org/privileged-and-non-privileged-instructions-in-operating-system/)
Topic No : 9 System Structure
Next Topic : [[Intro to Process Management]]

##### The instructions are divided into two categories : Privileged and non privileged

### Privileged :
These are only executed by the OS Kernel or a privileged process, such as device drivers.
These requires direct access to the hardware for the program to execute, So they have to be running on kernel mode by OS to unrestricted by the System resource

#### What are Privileged Instructions?

> **The Instructions that can run only in Kernel Mode are called Privileged Instructions .**

### Non Privileged :
These instruction are executed in any process including the user level, These instructions are used for files and memory, and managing process control. Non privilege instructions are executed in user mode, which provide limit access to the process and does not interfere with others

### Difference

##### Access to resources : 
Privilege instructions have direct access to the System resources, while non privilege instructions have limited access

##### Execution Mode :
Privilege is executed in the kernel, while other is in user mode

##### Execution Permission :
Privilege require permission to get executed, while non-privilege does not required

##### Purpose : 
Non-Privilege are executed for the general purposes of the computer, Privilege are executed for low level operations

##### Risk :
Privilege instructions are risk as it have direct access to hardware, caught of vulnerability lead to the crush or shut down of the system. Non privilege are less risky

### Characters of Privilege Instructions

- If you try to run privilege instructions on the user level, it is treated as illegal and trapped in the OS
- It is responsible for the OS to set timer before giving the power to any user program. Thus if timer is over OS takes controls
- They are executed in a specific order to achieve correct operation


