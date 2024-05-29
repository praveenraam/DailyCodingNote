Article [Link](https://www.geeksforgeeks.org/microkernel-in-operating-systems)
Topic No : 5
Next Topic : [[]]

Micro Kernel is a Type of OS kernel where it will only provide the **most Basic kernel service** for the **OS like Memory Management and process scheduling**, while other services are **implemented in the User level**, the communication for the processes are done through message passing. This system is more modular and flexible than traditional one.

The main advantage of this type of Kernel architecture is that it is provides secure and stable environment for the OS. Only the essential works are takes place in the kernel space. Chances for the crashing of the kernel is very low as most of the ops are takes place in the User mode. Crashing in user mode doesn't affect the entire system

Since service are done in the User level, It is easy to add, remove, or replace services without effecting the other part of the System.

**Security** : The attack surface of the OS is reduced. making it more difficult for attacker to show vulnerability

**Disadvantages** : The major disadvantage of this architecture is that the message passing between the user level and kernel is slow than the direct system calls. This affects the High performance application. This high complexity of the Kernel make it difficult for the development and maintenance of the OS.

**Overall** : The Micro kernel comes with the more secure and flexibility but with the compromise of some performance. The choice between the monolithic kernel and micro kernel is as per the requirement of the Operating System

**Kernel is core part of the OS**. where it acts as the bridge for the application and the Hardware. It is the first program to start after the Bootloader.

---
## What is micro kernel

The micro kernel is a classification of kernel. As a kernel it manages the system's recourses
But in the micro kernel , the user's service and kernel services are stored in different address space. The user services are kept in the user address and kernel services in the kernel address space. This lead to reduce in the over all size of the OS

The communication between the user program and the user service process is through the message passing. Thus it reduce the speed of the kernel. 

The OS remains unaffected during the fail of the user service, that they are separated from the kernel space

This add an advantage of expandible. if any new service are about to add, that is easily updated in the user space, no modification required for the kernel space.

---
## Micro kernel architecture

 The micro kernel is the core of the OS, that means that is handles the most important tasks only.
 Thus the only the important services are in the kernel and others are in the rest of OS System application program. Hence, the user can easily interact with those not important task with the Software application program 

The services handled by the kernel are 
 - Inter process communication 
 - CPU scheduling
 - Memory management

---
## Key features of the micro kernel

##### Small and simple kernel 
The microkernel is designed to be small and simple as it handles important and few tasks repeatedly like memory management, Process and communication. 

##### Modular design 
Most of the services were moved to the user mode, they can be loaded and unloaded as needed. This make it modular and flexible design , thus adding and removing process or a function is easier

##### Message passing 
The communication between the different parts are done by message passing. rather than the Shared memory. This provide more secure and reliable way to communicate.

##### Extensibility 
Incase if we need to add a new functionality to the OS. That new service is added to the user address space without modifying the kernel space itself.

##### Security 
By separating the most important functionality from kernel to user level, kernel will be more secure that the bugs and vulnerability in the user level doesn't affect the kernel

## Advantages of Micro kernel architecture

- More secure, as the risk of the vulnerability attacks are reduced.
- Better system stability, as crushes in user level processes doesn't affect the entire system
- More modular and flexible, make it easier for the OS customization

## Disadvantage of micro kernel architecture

- Slower message passing between user level process can affect the performance while the high performance application
- Increased complexity due to modular design making it difficult for the developer to develop and maintain
- More use of Memory compared to Monolithic kernel
- Optimization of the performance is limited due to separation of the kernel and user level processes

---
## FAQ 

##### How does a micro kernel architecture make an OS more modular and flexible
Hence the services are implemented in the user level, which makes it easier to add, remove, replace the services without affecting the other parts of the system. Thus it makes the OS to be customized



