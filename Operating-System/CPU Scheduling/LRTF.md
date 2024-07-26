Article  [Link](https://www.geeksforgeeks.org/shortest-job-first-cpu-scheduling-with-predicted-burst-time/) [Link](https://www.geeksforgeeks.org/longest-remaining-time-first-lrtf-cpu-scheduling-algorithm/)
Topic No : 20 CPU Scheduling
Next Topic : [[Round Robin]]

LRTF - Longest Remaining time first 

### Types of Long Job first
![[Pasted image 20240726155805.png]]
This is an algorithm that follows non - preemptive algorithm, which is based on the burst time. The process are queue on burst time in descending as the name suggest. 


### Non Preemptive
#### Characters
- The scheduler picks the longest burst time process in the waiting queue. 
- If two process with same burst time then it is picked on FCFS basis. 

#### Algorithm
- **Step 1 :** Sort the process in descending in order of arrival
- **Step 2 :** choose the process with the highest burst time among all process
- **Step 3 :** Once execution is over, check for another process 
- **Step 4 :** Repeat the steps

The preemptive version will be in the next topic
### Preemptive

The preemptive version of LTRF is PLJF
**PLJF** - Preemptive Longest Job First

#### Characters
- Among all the process waiting, Algo picks the process with longest burst time
- If two process have same burst time, then it is picked on FCFS
#### Algorithm 
**Step 1 :** Sort in the descending order of the burst time of process
**Step 2 :** Choose the highest burst time process with less arrival time
**Step 3 :** For every unit of time compare the highest burst time of a process in the queue and the executing process remaining burst time
**Step 4:** Repeat the above steps

#### Example :
| Processes | Arrival time | Burst Time |
| --------- | ------------ | ---------- |
| P1        | 1 ms         | 2 ms       |
| P2        | 2 ms         | 4 ms       |
| P3        | 3 ms         | 6 ms       |
| P4        | 4 ms         | 8 ms       |

![[Pasted image 20240726162414.png]]

![[Pasted image 20240726162403.png]]

### Advantage :
- No other process are executed until longest process finishes
- all the jobs are complete at same time approximately

### Disadvantages :
- The average waiting time and TAT is very high
- This lead to convey effect
- The smaller process won't get executed easily. Thus, reduces the speed and performance
