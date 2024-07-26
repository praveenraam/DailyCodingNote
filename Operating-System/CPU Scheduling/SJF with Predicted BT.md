Article  [Link](https://www.geeksforgeeks.org/shortest-job-first-cpu-scheduling-with-predicted-burst-time/)
Topic No : 19 CPU Scheduling
Next Topic : [[LRTF]]

The SJF is an optimized algorithm with most optimal approach that have less waiting and turn around time but it is not practically implemented because the correct burst time can't be predicted  
  
## Methods to Predict Burst Time  
### Static methods  
##### Burst Time process size  
Let's assume that the we have an old process of size 200Kb executed in 20 units of time, Now we have a process a size of 201Kb which is yet to execute, now we consider 20 unit of time as it's burst time because of the almost same size  
##### Process type:  
-  ***OS Process:** Schedulers, compilers, program managers, and many more operating system processes are examples of processes. Typically, their burst time is shorter—between three and five units of time.  
-  **User Process:*** User processes are those that are started by users. The following three categories of processes are possible.  
	-   Interactive processes are those that interact with the user or whose execution is entirely dependent on human input.  
	-  Foreground Process: These are the processes that users employ to complete tasks such as using Microsoft Office, editors, utility software, etc.  
	-  Background Process  
  
  