Article [Link](https://www.geeksforgeeks.org/introduction-of-system-call)
Topic No : 4 System Structure
Next Topic : [[MicroKernel]]

## Introduction

In computer, the System call is a **programmatic way of request the service to the kernel** of the OS
The system call is the way to interact with the OS, this is the only way to enter the kernel

System call provides the interface between the process and the OS

The user's **program can interact with the System** through the System call. The system call is written in an high level language like C or Pascal or assembly language.

The OS handles the request and return it back to the program. These System calls are essential for the proper functioning of the Operating System. 

Without the system call, each program need to implement a way to reach the OS for the service

## Important Note

When you make the System call for a program, it switches from **user mode to the kernel mode**, where in the kernel mode it has the **access to all the system resources including the full advantage of hardware**

If the program crashes during the run time in the kernel Mode , the entire system also crashes or come to the halt but in the user mode if program crash nothing happens.

---
## Functions of System call 

#### Interface : 
System call provides the interface for the user's program and OS

#### Kernel Mode : 
when system call is made , the user's program is temporarily moved from user mode to the kernel mode where it make full use of the system resource, hardware

#### Context switching :
System call requires a context switching, which involves changing the state of current process and switches to the kernel mode, which can impact system's performance and turning back to user mode

#### Error Handling : 
System call return the error code indicate the problem with Requested services
Program must check for the errors and handle them 

#### Synchronization : 
System call can be used to synchronize the Network, shared resources.

--- 
## System call advantage 

##### Access to hardware : 
System call allow program to access the hardware resources for the process

##### Memory management :
System call allow program to allocate and deallocate and also allow memory mapped hardware

##### Process management : 
System call allows to create and terminates the process, as well as manages the communication

##### Security : 
It have the privilege to modify the access for the program like administrator access, roles

##### Standardization : 
System call provides standardization for programs to interact with the OS, with ensuring the consistency and compatibility across the Hardware

--- 
## How does System call works

While running a program, the program needed to do some special things which can't be done without the permission of the OS (like reading and writing a file and information from the hardware). 

There are some predefined instructions to make a call to OS. These instructions are called System calls. The program make that system call when needed

When the OS sees the system call, It recognize it that program need a help. It stops the executing program and give all their controls to them which is called kernel mode.

Now the OS performs the operation that is requested by the program.

After performing those special operations, OS goes back to the program where it is stopped

--- 
## Examples of System calls

|Process|Windows|Unix|
|---|---|---|
|Process Control|CreateProcess()<br><br>ExitProcess()<br><br>WaitForSingleObject()|Fork()<br><br>Exit()<br><br>Wait()|
|File manipulation|CreateFile()<br><br>ReadFile()<br><br>WriteFile()|Open()<br><br>Read()<br><br>Write()<br><br>Close()|
|Device Management|SetConsoleMode()<br><br>ReadConsole()<br><br>WriteConsole()|Ioctl()<br><br>Read()<br><br>Write()|
|Information Maintenance|GetCurrentProcessID()<br><br>SetTimer()<br><br>Sleep()|Getpid()<br><br>Alarm()<br><br>Sleep()|
|Communication|CreatePipe()<br><br>CreateFileMapping()<br><br>MapViewOfFile()|Pipe()<br><br>Shmget()<br><br>Mmap()|
|Protection|SetFileSecurity()<br><br>InitializeSecurityDescriptor()<br><br>SetSecurityDescriptorgroup()|Chmod() <br><br>Umask()<br><br>Chown()|


## FAQ

- How does the System call works
	When a program executes a system call, it switches from user mode to kernel mode. This is invoked by the Specific function or interrupting instruction provided by the OS                         Once in the kernel mode, It performs the requested operation and executed in the behalf of the program and the program is switched back to the user-mode.

