Article [Link](https://www.geeksforgeeks.org/states-of-a-process-in-operating-systems/)
Topic No : 12 System Structure
Next Topic : [[Process Scheduler]]
##### PCB is a data structure used by the OS to store the information about the process.

As OS Supports multi tasking, it need to manage and track the details about the process. While creating a process OS generates a PID for the process. 

## Structure of PCB

The PCB contains many important piece of information needed to manage process efficiently

![[Pasted image 20240721161814.png]]

#### Pointer :
It is a stack pointer that is needed to update every time it switches it's state from state.
#### Process State :
It represent the current state of the process
#### Process Number :
It is the Unique ID of the process helps for the tracking of OS, it is given by OS. 
#### Program counter :
Program counter have the address of the next instruction to be executed.
#### Register :

#### Memory limit :
This field contains the information about the memory management system used by the OS. This includes page table, segment table.
#### List of open files :
Contains the list of files opened by the process.

![[Pasted image 20240721163117.png]]

## Additional information of PCB

#### Interruption Handling :
PCB also contains the information about the interrupts of that process may be have generated and how they are handled by the OS
#### Context Switching :
PCB plays an important role in context switching process, where stores the context of the current process and it restore the state for next process
#### Real time System :
Real time system also contains the information about the deadlines and priority of the process, to ensure the time - crucial processes are executed in timely manner
#### Virtual Memory Management :
It also contains the information about the memory management, such as page table page fault handling
#### Inter-Process communication :
The PCB contains info about the shared resources, and the channel for the communication
#### Fault tolerance :
Some OS uses multiple copies of PCB to provide fault tolerance in case of hardware failure

## Location of PCB

The PCB is stored in special part of the memory that cannot be accessed by the normal user.
This is because it holds the information about the process. Some OS stores it at the start of the kernel stack for process, also it is safe spot.
