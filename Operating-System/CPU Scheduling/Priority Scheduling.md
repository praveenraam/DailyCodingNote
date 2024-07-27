Article  [Link](https://www.geeksforgeeks.org/selfish-round-robin-cpu-scheduling/)
Topic No : 23 CPU Scheduling
Next Topic : [[Starvation and Aging]]
### What is Priority scheduling 

It is commonly used scheduling algorithm in batch system. Each process is assigned with a priority value. The highest priority will be executing at first, incase of same priority FSFC basis will be used to pick the process.

Priority can be changed on memory requirement, time requirement or any other resources.
Also decided on the ratio of Average I/O to average CPU burst time'

### Approach 

1- First input the processes with their burst time 
   and priority.
2- Sort the processes, burst time and priority
   according to the priority.
3- Now simply apply [FCFS](https://www.geeksforgeeks.org/program-fcfs-scheduling-set-1/) algorithm.

![[Pasted image 20240727160729.png]]

### Starvation :

The problem with the priority based scheduling is infinity block. This can be solved using aging technique.

**The aging technique is gradually increasing of priority of processes that are waiting for long time**

### Example :

![[Pasted image 20240727161737.png]]

##### Gantt Chart :
![[Pasted image 20240727161754.png]]

<pre>
Process_no Start_time Complete_time Turn_Around_Time Waiting_Time  
1           1           4              3              0   
2           5           10             8              3  
3           4           5              2              1  
4          10           17             13             6  
5          17           21             16             12  
Average Waiting Time is : 4.4   
Average Turn Around time is : 8.4
</pre>

