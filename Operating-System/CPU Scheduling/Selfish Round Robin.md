Article  [Link](https://www.geeksforgeeks.org/selfish-round-robin-cpu-scheduling/)
Topic No : 22 CPU Scheduling
Next Topic : [[Selfish Round Robin]]

### What is SRR ?
- The SSR is a modified version of the traditional round robin scheduling algo. 
- The SSR motives is to **give better service for the process that are executed once** while than the new arriving process
- There are two waiting list namely **NEW and ACCEPTED** 
- The new process wait while serving to the accepted process. The priority of the new process is increased by **A** and while accepted priority is by **B**

### Does fairness is followed in SSR 

SSR gives the same time quantum for all the process, which is achieved by RR and once the process is over it is placed queue, and the next process is executed

### Will SSR suitable for real time ?

No, SSR can't be used in real time system as it requires strict time constraints. The high priority process must have their CPU time, which is not possible in SSR

### Approach

- The processes are into two queue : **NEW and ACCEPTED**
- The priority of the new process are increased by **A** and the accepted are by **B**, once the priority of the new process reach the priority of Accepted, new process is executed
- If all the process are completed, high priority new process is executed
