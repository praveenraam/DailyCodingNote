Article [Link](https://www.geeksforgeeks.org/program-for-shortest-job-first-or-sjf-cpu-scheduling-set-1-non-preemptive/)
Topic No : 18 CPU Scheduling
Next Topic : [[SRTF (SJF)]]

The short job first, is a algorithm that picks the process with the smallest execution time (burst time), also known as Short job next , this can be done in both preemptive and non preemptive ways

### Characters of SJF Scheduling(Non Preemptive)

- This have the smallest waiting time among the all algorithms
- It's a greedy algorithm
- Can cause starvation if short process keeps coming, can be solved using ageing
- This can be used only if the accurate burst time is known

### Algorithm 

- Sort all the process based on arrival
- Pick the process with smallest execution time
- Repeat the algo

![[Pasted image 20240724142633.png]]

### Advantages
- SJF is better than [[FCFS CPU Scheduling]]
- This is used for long term scheduling
- SJB is optimal in avg. TAT

### Disadvantage
- SJB may cause starvation and increase turn around time
- Completion time should be known earlier where it is hard to predict
- Sometime, complicated to predict length of CPU request

 Shortest Remaining Time First ( Preemptive version of SJF )