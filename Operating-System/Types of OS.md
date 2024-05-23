Article [Link](https://www.geeksforgeeks.org/types-of-operating-systems)
Topic No : 3
Next Topic : [[System Call]]
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

![[Pasted image 20240523095928.png]]

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


## Real-Time OS

These are the types of OS where the time between the request and the response is very less. They are used in the field were the small time delay is not accepted.
They are used in the field of Air traffic control, automatic parachute, missile systems, Scientific experiments, medical imaging systems.

![[Pasted image 20240523085108.png]]
##### Two types of Real-Time System
- **Soft Real-Time system :** They are used for using software applications
- **Hard Real-Time system :** They are for strict constraints where the failure may end in bad cause.  


## Most Used OS

#### Windows 

It is referred as Microsoft Window, this is developed and maintained by the Software Giant Microsoft company, many of the personal computer are with Microsoft, where from the childhood peoples are trained to use the windows.

###### Advantage : 
- The most of the hardware produces will be supporting Windows and all the primary system comes with the Windows OS
- **Game Runner** : Windows supports most of the games and it is best for the game lover as it supports most of the popular games
- **Ease of Use** : This is very user friendly for the people to use and it have many pre build software which is used primary by the entertainment purposes
###### Disadvantages : 
- **Expense** : This cost more for a common user, where he has to spend 12000 INR for buying the latest version
- **Poor Security** : The security in the Window in the older version were very worst, as peoples are forced to buy an Anti-Virus Software. Compared to the competitors like MacOS , Linux it is less secured
- **Not reliable** : Windows started to lag with time and eventually needed booting

#### UNIX

UNIX is a multitasking and multi user OS. The OS is completely written in C language , allowing it to serve in numerous platforms

###### Advantage : 
- It has very efficient Virtual memory system
- The OS is the real portable system
- It has high level authentication with fully secured environment

###### Disadvantage : 
- This is primary uses for the developer and techies , it cannot be used by the common peoples 
- It is command line interface with shell and kernel, where peoples find tricky while handling the names
- you should have the knowledge to commands and main design to interact with the OS


#### Linux

The Linux's concept is derived from the UNIX OS, where is the most prominent and open source OS for the personal computers. It is build using the Linux kernel for desktops and servers. This is first developed for the Intel x86 Architected computers

The Top Linux are Ubuntu, Fedora, RedHat

###### Advantage :
- **Free of cost** : This is an Open source software where people can use it in a free of cost
- The OS is very lite and easy for the PC to run
- It is one of the Most secure OS out
- It is also designed for multitasking and multi user and runs without lags
###### Disadvantage : 
- It is not user friendly as like windows, users struggle for few days to adapt the OS
- It is not for the gamers as it doesn't for high graphic games
- This comes with lot of versions from lot of developers, there will be lot of confusions choosing the version to use

#### Android 

This OS is not a desktop, it is used in the Mobile phones, most of the top mobile brands build or customize their OS on the top of android. The vanilla android version is called Stock android. this is owned by tech giant google

#### iOS

This is also an another mobile phone OS where it is only used in the mobile phones produces by the Company **Apple**. iOS is very secure and protected while compared to the Android. It is developed by the Company Apple itself. It is mainly knows for the user experience.

#### MacOS 

The MacOS is only for the laptops of Apple. It is known for its sleek design and integration with the other Apple products


