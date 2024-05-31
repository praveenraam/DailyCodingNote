Article [Link](https://www.geeksforgeeks.org/monolithic-kernel-and-key-differences-from-microkernel/)
Topic No : 6
Next Topic : [[Kernel InOut Sub-system]]

This kernel was a simple kernel system where the kernel directly controls all the functions. All the system recourses are accessible for the kernel. Every part of the OS is within the kernel in monolithic System. It was introduced in 1970.

This is also called as Monolithic Operating System. This is an outdated system that bank employee for menial jobs, where all the components are managed by the monolithic kernel, which functions are virtual machine.

## What is Monolithic Architecture

In monolithic architecture, The OS kernel is designed to provide all the operating system services including memory management, process scheduling, device driver and file system. That means all the code runs in kernel space, with no separation between kernel and user level processes

![[Pasted image 20240531184052.png]]

**Advantage** : This can provide the high performance, since system call is directly to the kernel without the overhead message passing between the kernel and user level processes

**Disadvantage** : This is also turns to be the disadvantage for the architecture. That becomes less secure and stable for the Operating System. Since all the code runs in the kernel space, any bugs or vulnerability in the kernel can affect the entire system. Incase if the user level process crushes, it bring the system halt, since there is no separation between the user level and the kernel.

---
## Monolithic vs Micro kernel 

Like the micro kernel, monolithic kernel is also a classification of kernel, where it manages the system recourses between application and hardware, but the User space and kernel space are kept under same address space unlike micro kernel where user space are stored in separate address space from the kernel address space.

As Monolithic kernel provides CPU scheduling, memory management, file management and other OS functions under same memory space for both user and kernel processes, it gives high performance and execution is faster

##### Advantages 
- It manages the CPU scheduling, memory management, file management and other functions through direct system calls
- It runs the entire system in a large single memory space
- It is a single static binary file. **Example :** Linux, Unix, Open VMS

##### Disadvantages 
- The major error in the system is that if a service fails, it lead to the failure of the entire system.
- If you need to add a service, the entire system needed to be modified

### Key Difference

| Service        | Monolithic kernel                                                               | Micro Kernel                                                                                                                                   |
| -------------- | ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| System Service | All the services run in the kernel space (single address space)                 | Only the basic services are done in kernel, while other service running in user level space                                                    |
| Performace     | The performance of the monolithic kernel is faster and efficient                | The performance is slower than the monolithic kernel as the communication is slower through message passing between user level and kernel      |
| Modularity     | It has less modular than microkernel, as modification in service is difficult   | It has more modular as the adding and removal of service is easy to do without affecting other parts                                           |
| Security       | It is less secure, as small bugs and vulnerability can affect the entire system | This is considered safer, as the failure at the user level wont affect the entire system                                                       |
| Development    | Developing a monolithic kernel is easier as the architecture is simple          | It will be more difficult for the development as microkernel is complex with the user level and kernel spaces and communication has to be done |

| Basics                | Micro Kernel                                                                  | Monolithic Kernel                                                                                            |
| --------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Size                  | Smaller in                                                                    | Larger as OS and user both lie in the same address space.                                                    |
| Execution             | Slower                                                                        | Faster                                                                                                       |
| Extendible            | Easily extendible                                                             | Complex to extend                                                                                            |
| Security              | If the service crashes then there is no effect on working on the microkernel. | If the process/service crashes, the whole system crashes as both user and OS were in the same address space. |
| Code                  | More code is required to write a microkernel.                                 | Less code is required to write a monolithic kernel.                                                          |
| Examples              | L4Linux, macOS                                                                | Windows, Linux BSD                                                                                           |
| Security              | More secure because only essential services run in kernel mode                | Susceptible to security vulnerabilities due to the amount of code running in kernel mode                     |
| Platform independence | More portable because most drivers and services run in user space             | Less portable due to direct hardware access                                                                  |
| Communication         | Message passing between user-space servers                                    | Direct function calls within kernel                                                                          |
| Performance           | Lower due to message passing and more overhead                                | High due to direct function calls and less overhead                                                          |
