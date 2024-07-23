Article [Link](https://www.geeksforgeeks.org/program-for-fcfs-cpu-scheduling-set-1/)
Video [Link](https://youtu.be/MZdVAVMgNpA?si=5_30Ukit0zP9dE49)
Topic No : 16 CPU Scheduling
Next Topic : [[Convoy Effect]]


First In, first out, which is knowns as First come, first serve (FCFS).

This is a simple algorithm where the process comes are order and executed one by one by their arrival order
#### Terms
- Burst time or Execution Time : Time taken to execute the process
- Arrival Time : Time at which process arrives to queue
- Turn Around Time : Time the process spend on the queue and CPU
- Waiting Time : Time spent while waiting to execute 
- Response Time 
- Unit : Measuring term
### How to compute below times

- **Completion Time :** Time at which process complete the execution
- **Turn around time :**  Time difference between completion and arrival time (CT-AT)
- **Waiting Time :** Time difference between turn around and burst time (TAT-BT)
- **Response Time :** Time difference between time process start executing - arrival time
- **Average TAT :** Total TAT divides by no of process
- **Average WT :** Total WT divides by no of process
Ex 1 :
![[Pasted image 20240723172649.png]]

Ex 2 : 
![[Pasted image 20240723175135.png]]
![[Pasted image 20240723175151.png]]
### Imp Points :
- It is a non preemptive Scheduling
- Average waiting time while using this algo is not optimal
- Cannot use resources in parallel
