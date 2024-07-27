## MLQ Scheduling 

MLQ -> Multi Level Queue scheduling algorithm

There are algorithm that are used for situations where process are easily classified into groups

This rises when the process in the queue is divided into different class that has their own scheduling
**Example :** The common divisor is Background and foreground processes, here is the place where we use multi level queue scheduling algorithm

### Features of MLQ

- In MLQ , the tasks are placed in **different queue based on their priorities**, high priority process are placed in queue with high priority and low priority process are placed in low priority queue
- Priorities are assigned based on their type and characters. For example : Interactive process like input and output have higher priority than batch process
- Preemptive is allowed in MLQ scheduling, Low priority process are removed for the high priority processes
- Different scheduling algo can be used for different algorithms 
- This algorithm is customizable to meet the requirements
- MLQ provides the fairness for all process based on priority and requirements
-  A feedback mechanism is implemented to adjust the priority of the process based on the behavior over time. Example : If interactive process waits in the low priority queue for long time, it's priority is increased to ensure it's execution time manner

### Example :

**Ready Queue** is divided into separate queues for each class of processes

![[Pasted image 20240727185115.png]]
- **System Processes:** The CPU itself has its own process to run which is generally termed a System Process.
- **Interactive Processes:** An Interactive Process is a type of process in which there should be the same type of interaction.
- **Batch Processes:** Batch processing is generally a technique in the Operating system that collects the programs and data together in the form of a **batch** before the **processing** starts.

Each queue have different type of process and own scheduling algorithm
### Advantages :
- Giving fair chance for all the process
- Customizable
- Priority are assigned on their type, character and requirement
- It is a preemptive algorithm
- Since all process are separated into respective queue, it is less overhead
- This algo give preference to the low priority task when the CPU is idle. This ensure the utilization of CPU time

### Disadvantages :
- It is inflexible 
- There may be complexities in adding multiple scheduling algorithms to different queue
- Some process may end up in starvation as if high priority queue never be empty

## MLFQ 

MLFQ -> Multilevel Feedback queue Scheduling algorithm

The MLQ and MLFQ is same in all the ways except where MLFQ allows the processes to move between queue on requirements

The only advantage of MLQ over MLFQ is it is less overhead due to permanent assign of processes in their respective queues

### Features other than MLQ
- The priority is changed dynamically based on the behavior of the process, such as how much CPU time it has used or how often it has been blocked. Higher-priority processes are given more CPU time and lower-priority processes are given less.

### Advantage 
- It is flexible
- It allows different process to move different queue
- It prevent starvation by moving process to different queue
### Disadvantages 
- It produces more CPU over head
- It is most complex algorithm

### Example
Now, look at the diagram and explanation below to understand it properly
![[Pasted image 20240727192406.png]]

Now let us suppose that queues 1 and 2 follow [round robin](https://www.geeksforgeeks.org/program-round-robin-scheduling-set-1/) with time quantum 4 and 8 respectively and queue 3 follow [FCFS](https://www.geeksforgeeks.org/program-for-fcfs-cpu-scheduling-set-1/).

Implementation of MFQS is given below – 

- When a process starts executing the operating system can insert it into any of the above three queues depending upon its **priority**. For example, if it is some background process, then the operating system would not like it to be given to higher priority queues such as queues 1 and 2. It will directly assign it to a lower priority queue i.e. queue 3. Let’s say our current process for consideration is of significant priority so it will be given **queue 1**.
- In queue 1 process executes for 4 units and if it completes in these 4 units or it gives CPU for I/O operation in these 4 units then the priority of this process does not change and if it again comes in the ready queue then it again starts its execution in Queue 1.
- If a process in queue 1 does not complete in 4 units then its priority gets reduced and it is shifted to queue 2.
- Above points 2 and 3 are also true for queue 2 processes but the time quantum is 8 units. In a general case if a process does not complete in a time quantum then it is shifted to the lower priority queue.
- In the last queue, processes are scheduled in an FCFS manner.
- A process in a lower priority queue can only execute only when higher priority queues are empty.
- A process running in the lower priority queue is interrupted by a process arriving in the higher priority queue.