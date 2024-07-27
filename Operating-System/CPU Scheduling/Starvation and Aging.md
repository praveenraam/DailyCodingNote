Article  [Link](https://www.geeksforgeeks.org/selfish-round-robin-cpu-scheduling/)
Topic No : 24 CPU Scheduling
Next Topic : [[HRRN Scheduling]]

### What is starvation :

The starvation occurs when processes are Out of resources in CPU because other process were using it. 

Starvation or indefinite blocking is a phenomenon associated with priority scheduling algorithms, in which process ready for CPU can wait to run indefinitely because of low priority

### Difference between deadlock and starvation :

- Deadlock is when no process in the set able to move because occupancy of required resources by some other process.
- Starvation is when process wait for an indefinite of time to get to execute
- When deadlock occurs no process can make progress, while in starvation apart from victim process other process can progress or proceed

### What is ageing

Aging is a technique of gradually increasing the priority of processes that wait in the system for a long time. Operating systems employ ageing as a scheduling approach to keep them from starving. 

### Limitation of Ageing 

- There will be increased in complexity of the the scheduling algorithm.
- Frequent change in in priorities of process, which reduces the overall efficiency of algorithm
- This is very unpredictable as the rate of increase of the
- Aging does not gives fairness for the newly coming processes