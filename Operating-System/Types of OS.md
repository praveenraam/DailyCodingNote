Article [Link](https://www.geeksforgeeks.org/types-of-operating-systems)
Topic No : 3
Next Topic : [[]]
## Batch Operation System

They don't interact to the computer directly, They group the **similar type of jobs or task into a group** of batches, one after every group other runs.

This is used for performing the similar type of tasks

## Multi-programming OS

No interaction can be made with the user

This keeps the no of programs in the main memory and **keeps on running any one** of the program

##### Advantages 
- It reduces the response time
- It increases the **throughput** ( process passing through a system) of the system

## Multi-processing OS

This is a OS where there will be multiple CPU that runs several programs

![[Pasted image 20240522105457.png]]

##### Advantages 
- If one CPU fail to do a process, it can be executed in another CPU
- It increases the throughput of the system
##### Disadvantages
- Due to the presence of multiple CPU, it is very complex design and to understand

## Multi-tasking OS

Multi tasking OS is a simple Multi programming OS with the Round Robin Scheduling System that can run multiple programs simultaneously

**Types of Multi-Tasking OS**
- Preemptive Multi-Tasking
- Cooperative Multi-Tasking

![[Pasted image 20240522105445.png]]

##### Advantages 
- Multiple programs can be run simultaneously 
- It has a proper memory management
##### Disadvantage
- The system may end up heating incase of heavy program at same time

## Time sharing OS

Each tasks are given time to get executed so that all the task are ran smoothly. This is an version of the multitasking OS where here it is executed line by line by a single user or multi users. This is called as quantum 

After the task is over the OS switches to the next task 

![[Pasted image 20240522112606.png]]

##### Advantages : 
- Each task gets the opportunity to get completed
- CPU idle time is reduced
- It allow multiple users to assign the task and utilize the hardware which increase in the resource sharing
- **Improved Productivity**: Time-sharing allows users to work concurrently, thereby reducing the waiting time for their turn to use the computer. This increased productivity translates to more work getting done in less time.
- **Improved User Experience**: Time-sharing provides an interactive environment that allows users to communicate with the computer in real time, providing a better user experience than batch processing
##### Disadvantages
- Reliability problem
- **Over heating** issue
- Data communication problem
- One must be taking care of the **security and integration** of the program and data
- **Complexity problem** because of the time sharing system
- **Risk of the Security** because of the multiple users login

## Distributed OS

These type of System are widely used one, where multiple Devices having different CPU, Memory are communicated through communication system which allow one user to access the data or file that is not present in his computer but present in some others computer

![[Pasted image 20240522113736.png]]

##### Advantage 
- One system failure won't affect the system, rest of them will be working properly
- Since all the resources are shared, it will be fast to communicate
- Delay in data process reduces
- Load on host pc will reduces
##### Disadvantage
- Failure of the main computer will lead to stop of the entire system
- These types of system are not available readily and are very expensive
- All the software are very complex and not easy understand 
