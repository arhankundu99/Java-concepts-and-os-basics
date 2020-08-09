# CPU Scheduling in OS

## Important terms
1) Arrival Time: Time at which process arrives in the queue.
2) Completion time: Time at which the process is completed
3) Burst Time: Burst time is the time taken by the process to run on the CPU.

```Completion time - Arrival Time = Burst time + Waiting Time```

4) Turn Around Time: Time difference between Completion time and Arrival Time.

```Turn Around time = Completion time - Arrival Time```

5) Starvation: Starvation is a phenomenon due to which a process can wait indefinitely due to low priority.

## Scheduling Algorithms:
1) First Come First Serve (FCFS): The process which comes first in the queue is executed first. Implemented using a FIFO queue. It can cause long waiting times.

2) **Shortest Job First Algorithm (SJF)**: The process which have low burst time are scheduled first. In case if a tie, FCFS is used. NOTE that it is non-preemtive algorithm (That means a process cannot interupt another process which is in execution). Average waiting times are low. Can cause Starvation

3) Longest Job First Algorithm (LJF): Similar to SJF except that high burst time processes are scheduled first. Non-preemtive algorithm.

4) Shortest Remaining time First algorithm (SRTF): It is the preemtive version of SJF Algorithm.Can cause starvation.

5) Longest Remaining Time First algorithm (LRTF): Preemtive version of LJF algorithm.

6) Round Robin Scheduling Algorithm: Here, the queue is treated as circular queue. The CPU assigns a fixed time to all the processes. If the current process cannot be completed during the fixed time, the CPU will send the unfinished process to the tail of the queue and starts executing next processes in the queue.

if the time assigned by the CPU to a process is very large, it acts a FCFS Algorithm.

7) Priority Queue Scheduling (Non preemtive): The process with higher priority is processed first. In case of a tie, FCFS is used. Can cause starvation

8) Highest Response Ratio Next (HRRN): The processes with high responses are scheduled first. This algorithm avoids starvation.

```Response ratio = (Burst Time + Waiting Time)/Burst Time```

Reference: <https://www.geeksforgeeks.org/cpu-scheduling-in-operating-systems/>


