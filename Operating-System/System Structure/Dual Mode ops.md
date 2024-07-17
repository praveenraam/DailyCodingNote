Article [Link](https://www.geeksforgeeks.org/dual-mode-operations-os/)
Topic No : 8 System Structure
Next Topic : [[Privileged and Non Privileged Instructions]]

## Impact of error in OS 

An error in a program can affect many process, it can modify the data of another program or even also effect the OS. So to ensure the proper execution, OS introduces two mode of operations.

In any OS, it is necessary to have Dual mode Operation for the better security, protection of the system.
## User Mode 

When the System is running an applications or application program, then the system is in user mode. if the application request a service from the OS or gives out a system call, then the application program is privileged to Kernel mode, once the requirement is completed it is back to the user mode

#### **Note:*** To switch from kernel mode to user mode, the mode bit should be 1.
User is restricted from the mode bit

![[Pasted image 20240716142143.png]]

## Kernel Mode 

When the system is loaded, During the boot time hardware starts in kernel mode, after the OS is loaded the application program is in user mode, there are lot of hardware protections provided by the kernel mode, if the application program in the user mode tries to access those hardware privileges it is treated as illegal and trap to OS. The trap or System is proceeded with the change of mode bit to 0 (kernel mode) and let it come to the 1 (user mode)

Some privileged instructions : 
- Handle Interrupts
- Mode switching
- I/O Management

## Need for the Dual Mode

- Not all the application programs requires the access to the hardware, So certain are hidden from the user
- All the bottom level programs are handled in the kernel mode, so it is required to have Dual Mode

***On simple words, the application program will be executed in the user mode unless it make a service request to the OS using system call, it is switched to the kernel mode by changing the mode bit from 1 to 0. Also the mode bit is changed back to the 1 after execution of the program***

