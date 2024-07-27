Article  [Link](https://www.geeksforgeeks.org/selfish-round-robin-cpu-scheduling/)
Topic No : 24 CPU Scheduling
Next Topic : [[]]

HRRN -> Highest Respond Ratio Next Scheduling algorithm

This is one of the most optimized algorithm. HRRN is done based on an extra variable called Response ratio. Given N processes with arrival and burst time, we have to find the average waiting time and waiting turn around time.

<pre>
Response Time = (W+S)/S
</pre>

### Characteristics 

- It is a non preemptive algorithm
- The criteria of HRRN is response ratio
- It is modification of SJB to reduce algorithm
- In comparison with SJB and HRRN is SJF pick the job with less burst time and HRRN is picked with Response Ratio

### Example 
|Processes|Arrival time|Burst Time|
|---|---|---|
|P1|0ms|3ms|
|P2|2ms|6ms|
|P3|4ms|4ms|
|P4|6ms|5ms|
|P5|8ms|2ms|

Till T = 9, there is no problem in picking process
P1 and P2 is completed executing

Now waiting time calculation : 

p3 -> (9-4) = (5+4)/4 = 2.25
p4 -> (9-6) = (3+5)/5 = 1.6
p5 -> (9-8) = (1+2)/2 = 1.5

So we execute P3 as it have the highest response ratio

like wise all the processes are selected

### Disadvantages

- The implementation of HRRN is not possible as it is not possible to find the correct burst time
- This may give overhead to the CPU


