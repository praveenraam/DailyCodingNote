Article [Link](https://www.geeksforgeeks.org/preemptive-and-non-preemptive-scheduling/)
Topic No : 15 CPU Scheduling
Next Topic : [[]]

Dispatcher is special program get executed after scheduler. When the short scheduler pick the job, the dispatcher takes the process to the ready or queue state.

## Role of Dispatcher

- The dispatcher give the control of the CPU to the process
- Dispatcher is communication worker who receives and transmits information to co-ordinate operations of other persona

## Difference between scheduler and dispatcher 

The situation comes in, where various process are in the CPU, as all the process can't takes place in the CPU. Now OS have to choose an order to execute the process which should follow an algorithm that is called as the Scheduler.

Once the scheduler picks the process and dispatcher take process to the ready queue and moves to running state. 

This means schedulers show which function to get to execution state.

![[Pasted image 20240722221728.png]]

	Ex : 4 processes are in ready queue P1, P2, P3, P4. Their t0,t1,t2,t3. FIFO algorithm algorithm is used. First scheduler picks p1 , dispatcher now picks the p1 from ready queue to running state, then now scheduler picks p2 to execute. dispatcher 