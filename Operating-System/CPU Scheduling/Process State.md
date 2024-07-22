Article [Link](https://www.geeksforgeeks.org/states-of-a-process-in-operating-systems/)
Topic No : 11 CPU Scheduling
Next Topic : [[Process Table and Process Control Block (PCB)]]

![[Pasted image 20240718111922.png]]
### New State :
In this state, the process is about to be created, but not created. This program is in the secondary memory that is about to pick by the OS to create process

### Ready State : 
After the new, the created process is moved to the main memory. Now the process is ready to get executed and waiting to CPU time. Processes in the ready state are maintained in the queue called ready queue.

### Run State : 
The process is chosen from the ready queue by the CPU for the execution. The program is executed in any of the Cores available in CPU (Cores are the place where the program is executed(processed)).

### Blocked or Wait State : 
This is the state where the program wait for the I/O request to complete or access from any file. This is done in main memory without the help of the CPU. Once the process is completed it is moved to the ready state.

### Terminate or Complete State : 
Process is killed by removing the PCB ([[#Process Table and Process Control Block]]). The resource allocated are freed or deallocated.

### Suspend Ready :
Process in the ready state is removed from the main memory to secondary by scheduler is said to be suspend ready. This is again can be moved the main memory

### Suspend block :
Process is moved to the secondary memory from which was performing I/O process. This is because of the lack in the main memory. When work is finished it goes to suspend ready.

### CPU and I/O Bound processes : 
If process is intensive in the terms of CPU Operations , it is CPU bound process, if it is intensive in terms of I/O operations then it is I/O bound.


## How a Process moves from one to another state

#### New to ready :
when the process is created, it is in new state, when the OS allocates the resources to it and it is ready for execution

#### Ready to running :
Once the CPU cores are available, the Scheduling algorithms will pick a process from the queue based on the multiple categories.

#### Running to block :
when the process waits for an another event to occur. it is moved to block state. A prime example is a process waiting for I/O operation.

#### Running to ready :
When a process is moved for the preempted by the OS, it is moved to running state. Ex : Arrival of a high priority process in ready queue, it is moved to the running state.

#### Running to terminal :
When the process is completes it is execution, or terminated by OS it moves to the terminal state.

