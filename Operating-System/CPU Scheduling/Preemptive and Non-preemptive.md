Article [Link](https://www.geeksforgeeks.org/preemptive-and-non-preemptive-scheduling/)
Topic No : 14 CPU Scheduling
Next Topic : [[Dispatcher and scheduler]]

## There are two types of scheduling :

### Preemptive Scheduling 

Preemptive scheduling is used when a process switches from the running state to ready state or vice verse. The resources allocated to the process is only for limited time and those were taken away. The processor goes back to the queue if the burst time is remaining. It stays in the queue and get chance to execute.

In simple, Preemptive scheduling allows the operating system to interrupt and reassign the [CPU](https://www.geeksforgeeks.org/difference-between-cpu-and-gpu/) to different processes

Ex : Round Robin, Short Remaining Time first, Priority(preemptive)

![[Pasted image 20240722183054.png]]

### Non Preemptive scheduling 

Non preemptive is when only process terminates or goes to the waiting state, once the resources are allocated the process stay in the core until termination or reaches wait queue. While execution it is not interrupted.

In simple,  Non-preemptive scheduling lets processes run to completion without interruption, simplifying the system but potentially causing [delays](https://www.geeksforgeeks.org/delays-in-computer-network/) for other tasks.

Ex : Short Job First , Priority(non preemptive)

![[Pasted image 20240722183109.png]]

## Key Difference 

#### CPU allocation : 
In preemptive, CPU is allocated to processes for limited time 
where here, CPU is allocated till the terminal or till switching to waiting state
#### Interruption :
In preemptive, The process is interrupted in middle of the execution
In non - preemptive, The process is not interrupted till terminal 
#### Overhead issue :
In preemptive, the arrival of high priority process and context switching and vice verse is overhead
where here, it don't have issue of context switching
#### Starvation :
In preemptive, the waiting for the low priority process is high
where here, If larger burst time process enters other all process have to wait
#### Shared Data :
Sharing data is possible in preemptive why it is associated, where there it is not possible

  
| Parameter           | PREEMPTIVE SCHEDULING                                                                                      | NON-PREEMPTIVE SCHEDULING                                                                                                                |
| ------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Basic**           | In this resources(CPU Cycle) are allocated to a process for a limited time.                                | Once resources(CPU Cycle) are allocated to a process, the process holds it till it completes its burst time or switches to waiting state |
| **Interrupt**       | Process can be interrupted in between.                                                                     | Process can not be interrupted until it terminates itself or its time is up                                                              |
| **Starvation**      | If a process having high priority frequently arrives in the ready queue, a low priority process may starve | If a process with a long burst time is running CPU, then later coming process with less CPU burst time may starve                        |
| **Overhead**        | It has overheads of scheduling the processes                                                               | It does not have overheads                                                                                                               |
| **Flexibility**     | flexible                                                                                                   | Rigid                                                                                                                                    |
| **Cost**            | Cost associated                                                                                            | No cost associated                                                                                                                       |
| **CPU Utilization** | In preemptive scheduling, CPU utilization is high                                                          | It is low in non preemptive scheduling                                                                                                   |
| **Waiting Time**    | Preemptive scheduling waiting time is less                                                                 | Non-preemptive scheduling waiting time is high                                                                                           |
| **Response Time**   | Preemptive scheduling response time is less                                                                | Non-preemptive scheduling response time is high                                                                                          |
| **Decision making** | Decisions are made by the scheduler and are based on priority and time slice allocation                    | Decisions are made by the process itself and the OS just follows the process’s instructions                                              |
| **Process control** | The OS has greater control over the scheduling of processes                                                | The OS has less control over the scheduling of processes                                                                                 |
| **Overhead**        | Higher overhead due to frequent context switching                                                          | Lower overhead since context switching is less frequent                                                                                  |
| **Examples**        | Examples of preemptive scheduling are Round Robin and Shortest Remaining Time First                        | Examples of non-preemptive scheduling are First Come First Serve and Shortest Job First                                                  |
