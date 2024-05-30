
This kernel was a simple kernel system where the kernel directly controls all the functions. All the system recourses are accessible for the kernel. Every part of the OS is within the kernel in monolithic System. It was introduced in 1970.

This is also called as Monolithic Operating System. This is an outdated system that bank employee for menial jobs, where all the components are managed by the monolithic kernel, which functions are virtual machine.

## What is Monolithic Architecture

In monolithic architecture, The OS kernel is designed to provide all the operating system services including memory management, process scheduling, device driver and file system. That means all the code runs in kernel space, with no separation between kernel and user level processes

**Advantage** : This can provide the high performance, since system call is directly to the kernel without the overhead message passing between the kernel and user level processes

**Disadvantage** : This is also turns to be the disadvantage for the architecture. That becomes less secure and stable for the Operating System. Since all the code runs in the kernel space, any bugs or vulnerability in the kernel can affect the entire system. Incase if the user level process crushes, it bring the system halt, since there is no separation between the user level and the kernel.

