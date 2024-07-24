Article [Link](https://www.geeksforgeeks.org/convoy-effect-operating-systems/)
Topic No : 17 CPU Scheduling
Next Topic : [[Short Job First]]

Convey effect only occurs in the case of FCFS Algorithm, where the whole OS slows

### What is Convey Effect

FCFS is non preemptive in nature unlike other algorithms. Once the process get to CPU it can't be taken out of the CPU other than the process get finished. This is lead to the Convey effect. 

Suppose if a heavy process with high burst time is in ready queue, other process with fewer burst time that are I/O bound process have to wait till the heavy process to get over.

### Measures to avoid convey effect in OS

To avoid convoy effect, preemptive scheduling like Round Robin Scheduling can be used, where the small process also get the even time to get executed.

#### Example of Convey Effect in OS 

Consider there are three process P1,P2,P3 and P3 have highest burst time
##### If P3 is in the queue, as it has longest burst time. The convey effect is caused to P1 and P2

| Process ID | Arrival Time | Brust Time | Completion Time | Turn Around Time | Waiting Time |
| ---------- | ------------ | ---------- | --------------- | ---------------- | ------------ |
| P1         | 1            | 1          | 42              | 41               | 40           |
| P2         | 1            | 3          | 45              | 44               | 41           |
| P3         | 0            | 42         | 46              | 46               | 4            |

Average waiting time is 85/3

##### If P3 is in the last of the queue, even though the length is 45 unit 
|Process ID|Arrival Time|Brust Time|Completion Time|Turn Around Time|Waiting Time|
|---|---|---|---|---|---|
|P1|0|2|4|2|0|
|P2|0|1|3|3|2|
|P3|1|42|45|44|2|
Average waiting time is 4/3

