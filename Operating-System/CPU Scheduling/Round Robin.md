Article  [Link](https://www.geeksforgeeks.org/program-for-round-robin-scheduling-for-the-same-arrival-time/)
Topic No : 21 CPU Scheduling
Next Topic : [[Selfish Round Robin]]

This is a new type of algorithm that does not depends on the burst time of the process

This algo follows an equal time slot system in a cyclic manner for the processes. It is preemptive version of FCFS algo

- It uses a time sharing technique
- The time the process is executed and follows preemptive method called time quantum
- If the process got executed in the given time, then it is terminated or else the process is moved to the ready queue

### Characters
- It is easy and simple algo and handles the starvation 
- It is preemptive as the process are removed after the time quantum and added to queue
- It has overhead of context switching problem

### Advantages :
- Every Process gets an equal opportunity in CPU
- The newly created process is added to end of queue
- During this algo, a particular time quantum is allocated to each process
- Once the time quantum over, the process is rescheduled

### Disadvantages :
- The waiting time and response time is larger
- The low through is out ( Output )
- There is lot of context switching
- Gantt chart is big 
- time will be consumed for small process

### Example 

| **Process** | **Burst Time** | **Arrival Time** |
| ----------- | -------------- | ---------------- |
| P1          | 5 ms           | 0 ms             |
| P2          | 4 ms           | 1 ms             |
| P3          | 2 ms           | 2 ms             |
| P4          | 1 ms           | 4 ms             |
![[Pasted image 20240726164053.png]]