Article [Link](https://www.geeksforgeeks.org/process-schedulers-in-operating-system/)
Topic No : 13 CPU Scheduling
Next Topic : [[Preemptive and Non-preemptive]]

Process schedulers are important component of the OS, where it is responsible for the order or time for a process to get executed during the multi tasking in one or more cores of the processor

## What is Process scheduling?

The process of managing the process in the queue, removal of process in the execution, and selecting another process for the execution in a particular strategy

It is very essential in the multi tasking OS, such as the OS that allow multiple process to get executed at a time.

## Categories of Scheduling 

#### Preemptive Scheduling :

A process can be removed from the execution and an another process with high priority is added to the core for the execution, once the high priority process is executed the removed process is executed again
#### Non-Preemptive Scheduling :

A process can't be taken out of the processor before getting executed.

## Type of Schedulers 

#### Long term or Job scheduler
It is responsible for taking the new process to the ready state, it controls the degree of multiprogramming(no of process present in the ready queue). This increases the efficiency by maintaining balance between CPU bound and I/O bound process. 

**Note : The job queue is implemented in Linked List**.
#### Short term or CPU scheduler 
It is responsible for selecting one process from the ready queue to running state. It only select the process, it won't load to running state. It is responsible for ensuring starvation due to high burst time.
#### Medium term scheduler
It is responsible for suspending a process from a scheduler. It remove the process from main memory to disk and vice versa. It also helps in maintaining balance CPU and I/O bound process. This reduce the degree of multiprogramming 

![[Pasted image 20240722210511.png]]
## Dispatcher 
- It is responsible for loading and unloading process from the processor's core selected by the Short term scheduler. 
- Context switching is done
- Switching to user mode
- Jumping to address of newly loaded program

