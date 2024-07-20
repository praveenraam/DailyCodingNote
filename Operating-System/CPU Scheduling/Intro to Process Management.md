Article [Link](https://www.geeksforgeeks.org/introduction-of-process-management/)
Topic No : 10 CPU Scheduling
Next Topic : [[Process State]]
### What is a process 
It is just execution of a program. The process is an activity

Ex : Write a code in a language, compile the program and running the binary code is the process

A single program can create many process when running multiple times

### What is Process Management

Process controlling is a key part in the OS. It is a task of handling how, when, and which process should takes place in based on the attentions and priorities. This includes stopping process and setting the important's of the process and many. 

The OS is responsible for start, stop and scheduling of the process not to get deadlocked, to synchronize, to inter process communication. There are lot of way to manage the process. This includes the resource allocation, process execution and efficient use of those resources while running multiple application programs.

### How does process look's like in Memory

A process in memory is divided into sections in the memory.

![[Pasted image 20240718093922.png]]

- **Text Section :** A process, sometimes know as the Text section. This includes the current process using the program counter
- **Data :** Contains the global variable
- **Heap Section :** Dynamic Memory allocation to process during it's runtime 
- **Stack :** It contains temporary data, like functions, parameters, return address and local variable

### States of Process

	   ![[Pasted image 20240718094935.png]]

- **New :** Newly created process or being created process
- **Ready :** After creation, it moves to ready state (Ready for execution)
- **Running :** Currently running in CPU (One process for each Processor)
- **Wait :** On execution, when process request I/O
- **Suspended Ready :** When Ready queue is full, process is moved to Suspended queue
- **Suspended Block :** When the wait queue becomes full.
### Character of a Process 

- **Process ID** : Unique identifier given by the OS
- **Process State :** Represent the state of the process 
- **CPU Registers :** CPU Registers must be saved when in and out of CPU
- **Accounts Information :** Amount of CPU used for execution, time limit, execution ID
- **I/O Status Information :** For example, device allocated to process.
- **CPU scheduling Information :** It contains info about priority, time limit.

### Process Operations 

The various tasks done by the OS to manage process is Process Operations
![[Pasted image 20240718100313.png]]

**Process Creation :** It is creation of new process. This is instance of the program which that can executed independently

**Scheduling :** One the process is ready, it is added to the Queue. Scheduler's job is to pick the process to execute.

**Execution :** It means the process is executed in the processor.

**Killing the process :** Once the process is complete, OS remove Process control block (PCB)

### Context Switching 

Saving the context of one process and loading an another process is called context switching.

##### When Context switching happens
- When a high priority come to the queue
- An Interruption in program
- While using Preemptive scheduling

**Note : Don't get confuse with context and mode switching**

### CPU Bounding vs I/O Bounding 

When time spent in the CPU or in run time is higher by the process, it is CPU Bounding, while time spend in the I/O process than CPU time then it is I/O Bounding 

