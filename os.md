# CPU Scheduling in OS

## Important terms
1) Arrival Time: Time at which process arrives in the queue.
2) Completion time: Time at which the process is completed
3) Burst Time: Burst time is the time taken by the process to run on the CPU.

```Completion time - Arrival Time = Burst time + Waiting Time```

4) Turn Around Time: Time difference between Completion time and Arrival Time.

```Turn Around time = Completion time - Arrival Time```

## Scheduling Algorithms:
1) First Come First Serve (FCFS): The process which comes first in the queue is executed first. Implemented using a FIFO queue.

2) Shortest Job First Algorithm (SJF): The process which have low burst time are scheduled first. In case if a tie, FCFS is used. NOTE that it is non-preemtive algorithm (That means a process cannot interupt another process which is in execution)

3) Longest Job First Algorithm (LJF): Similar to SJF except that high burst time processes are scheduled first. Non-preemtive algorithm.

