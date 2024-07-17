Article [Link](https://www.geeksforgeeks.org/kernel-i-o-subsystem-in-operating-system/)
Topic No : 7 System Structure
Next Topic : [[Dual Mode ops]]

There are several services that are related to the I/O system by the kernel such as I/O scheduling, buffering, cache, spooling, device reservation and more. It is build on the hardware and device driver infrastructure. It is responsible for the protecting itself from malicious user and errant processes

#### I/O scheduling 

To schedule a set of I/O requests means to determine the good order in which to execute them. **The scheduling improves the over all performance of the system, can give access to permission fairly to all processes.** This will lead to reduce in the overall average waiting time, response time.

OS developers makes the schedule by maintaining a wait queue of request for each requests

#### Buffering 

Buffering is a memory area where the data transferred between two devices or between device and application. Buffering is done for three reasons
- To match the speed of transfer between the producer and the consumer
- Adaption of data for different transfer size
- To support copy semantics for the application
#### Cache 

Cache memory is the a space where it hold the data that is very fast. Access to the cache memory is easier to access the original file. The instructions of the current running processes stored in the disk, cached in primary memory and then it is copied to the CPU's secondary memory and primary cache. 

The main difference between the buffer and cache is buffer stores the copy of data of existing item and cache is same on the faster storage

#### Spooling and device reservation 

The spool is a buffer that holds the output of device, A printer can serve only one task at a time so the data sent to the system has to be controlled. This is taken care by the OS by preventing all output continuously to the printer. When application finishes printing , and then the next is sent in the queue system.

#### I/O protection 

A user may attempt to issue illegal I/O instructions to disturb the normal functions of the system. We can use various mechanism to ensure that disruption cannot takes place. 
To prevent it we define all the I/O instructions to be in privileged mode. The user cannot access it directly

#### Error Handling 
An OS that use the protected memory to guard against many kinds of hardware and application errors and bugs. So the complete system failure is not usual result of the each minor mechanical glitches, errors, I/O failures.

###### Error detection : 
The kernel I/O sub system has various mechanism to detect the errors happens in the I/O OS
###### Error Reporting : 
Once the error is detected, the Kernel I/O employs mechanism to report the error to the higher level of OS or to user level
###### Error Recovery Mechanism : 
Recovering from the I/O error is so crucial to maintain the system stability
###### User notification : 
Informing about the error happened to the user is essential for timely intervention
###### User alerts : 
Providing alerts to the users, either through the user interface or system notification, can prompt immediate attention to potential issue

### Advantages and Importance

One of the critical component of an OS is kernel's I/O Subsystem, which is in between of OS and I/O devices. It manages the request from the user application and translate them into the hardware commands 

#### Device Independence : 
The Kernel I/O provides device independence to the user's applications. It means that the application developer can write code independent of hardware problem as Kernel I/O subsystem takes care of the hardware details

#### Efficient memory management : 
This manages the I/O requests  and schedule them in an optimized way that use the available resources. This ensures that I/O devices are not over utilized.

#### Concurrency Management :
It manages the issue raised when multiples applications try to access the same device simultaneously, it gives exclusive access to application and allow multiple app's to share the device appropriately

## Disadvantages

#### Complex Implementation : 
This is a complex code that requires a lot of resources to maintain. Any issue in the I/O system can affect the performance and stability of the system/

#### Security Risks
It can be easily exposed if it is not implemented correctly. The attackers exploit vulnerabilities in the Kernel I/O system to gain un authorized access.
