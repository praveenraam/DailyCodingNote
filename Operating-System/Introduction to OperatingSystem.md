Article [Link](https://www.geeksforgeeks.org/introduction-of-operating-system-set-1/)
Topic Wise [Link](https://www.geeksforgeeks.org/operating-systems/)
Topic No : 1
Next Topic : [[Functions of OS]]
## Why we need an OS

- It acts an intermediate between the Hardware and the user
- OS is a software managing the hardware
- OS is the only program that runs all time on the computer( called kernel ) with all else is application program



---
## Characteristics of OS

#### Device Management : 
- The operating system keep tracks of the device that are connected (Input and Output controller)
#### File Management : 
- It allocates and de allocates the resource and decide who get the resources
#### Memory Management :
- It keep tracking of the primary memory, and ensures who use which memory and not used memory
#### Processor Management :
- It allocates the processor to process and de allocates when process is not needed
#### Security : 
- It prevent the un authorized access and data using some protection techniques
#### Efficiency :
- The computer's OS uses the Computer potential efficiently and makes convenient for the user

--- 
## Functionality of OS
#### Resource Management :
- When parallel accessing happens in the OS means when multiple users are accessing the system the OS works as Resource Manager, Its responsibility is to provide hardware to the user. It decreases the load in the system.
#### Process Management :
- It is responsible for scheduling and terminating of a process, The concept of Scheduling in CPU will be learnt in upcoming topics
#### Storage Management : 
- OS have a storage manager that manages the various data including the hard disk
#### Memory Management : 
- It is management of primary memory, this keep track of how much memory used by the which task and it allocates it to the process or task
#### Security and Privacy ; 
- Privacy features is also provided by the OS with password and stopping the un authorized accesses
- It provide security from the malwares and attack of virus 

--- 
## Layering of OS

- Every computer needs an OS to run the other applications and programs
- The OS is responsible for the intaking the Input from the keyboard, mouse, and keep tracking of the files and giving the output for the displays or any other screens

![[Pasted image 20240521085751.png]]
**The extended machine is build on the top of the OS, this is responsible for the save, swapping and I/O process**

- It will be easy to modify, debug, test the OS module

---
## I/O System Management :

**I/O Traffic controller** is the module responsible for the I/O of the computer, it consist of the 
- Memory management component
- general device drivers
--- 
## Assembler

**Converts the assembly level program to the machine level program**

- The input for the Assembler is the assembly code the it convert it into an Object program
- Without the assembler it is hard for the programmer to write the code, without it people are only be able to write in machine level code which is consist series of **ones and zeros**

#### Compilers and Interpreters

- The compiler is a program that convert the high level languages (C,C++,Rust) to a machine code in the One Go
- The interpreters is a program convert to the machine level code line by line (Python, Pearl)
#### Loader

**The loader is a program that loads the Object program in the memory and prepare it for the execution** 

The Loader has three phases : 
- Load 
- Relocate 
- Link the object program 

--- 
## Components of OS 

### Shell 
Shell is the outer most layer of the operating System that handles the interaction between the user, **It is responsible for the interaction between OS and the user** 

- It is the communication way between them 
- Shell gives input for the user and interprets it for the OS
### Kernel
The kernel is the core of the OS, **All other components are depends on the Kernel** for the supply of the important services. The kernel is **primary component between the hardware and the OS**
##### Functions of Kernel
- Helps in I/O management
- Helps in management of Memory and Applications
- Helps in controlling the System calls
##### Types of Kernel 
- Monolithic kernel
- Micro Kernel
- Hybrid Kernel
- Exo kernel

--- 
## Difference between 32 and 64 bit OS 

| 32-Bit Operating System                                                                                          | 64-Bit Operating System                                                                 |
| ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| 32-Bit OS is required for running of 32-Bit Processors, as they are not capable of running on 64-bit processors. | 64-Bit Processors can run on any of the Operating Systems, like 32-Bit OS or 64-Bit OS. |
| 32-Bit OS gives a low efficient performance.                                                                     | 64-Bit Operating System provides highly efficient Performance.                          |
| Less amount of data is managed in 32-Bit Operating System as compared to 64-Bit Os.                              | A large amount of data can be stored in 64-Bit Operating System.                        |
| 32-Bit Operating System can address 2^32 bytes of RAM.                                                           | 64-Bit Operating System can address 2^64 bytes of RAM.                                  |

