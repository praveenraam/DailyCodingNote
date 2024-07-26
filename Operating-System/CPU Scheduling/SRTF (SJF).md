Article  [Link](https://www.geeksforgeeks.org/shortest-remaining-time-first-preemptive-sjf-scheduling-algorithm/)
Topic No : 18 CPU Scheduling
Next Topic : [[SRTF (SJF)]]

SRTF - Shortest remaining time first

We learn about SJF, now we implemented Preemptive algorithm in SJF, where for every unit of time we check the smallest execution time

This means once then smallest job is executing and their burst time is reducing, another small job with less execution of remaining burst time arrives, that will be the one process to execute

## Characteristics

- Preemptive : This is preemptive which means current running process can be removed if new process with less burst time arrives
- Dynamic : this means that it can adapt in change of the arrival of processes.
- Less Waiting time
- It has higher complexity than other scheduling algo like round robin and FCFS

### Approach 
- Find the process with smallest burst time
- reduce it's completion time by 1
- Check if it remaining completion time is 0
- Increment the counter of process complete
- Increase time lap by one

### Advantage :
- Only needed to check with the newly arrived process 
- Short process are completed quickly

### Disadvantages :
- Similar to SJF, can cause starvation
- Hard to predict the burst time accurately
