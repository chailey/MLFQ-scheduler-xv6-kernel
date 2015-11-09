# MLFQ-scheduler-xv6-kernel-
Implemented MLFQ scheduler with four priority queues; the top queue (numbered 0) has the highest priority and the bottom queue (numbered 3) has the lowest priority. When a process uses up its time-slice, it should be downgraded to the next (lower) priority level. The time-slices for higher priorities will be shorter than lower priorities.At the bottom queue of there are more than one process, they will be scheduled in Round Robin policy.

1.When a process is first created, it should be placed at the highest priority. Place this process at the end of the high priority queue.
At any given point in time, the highest-priority ready process should be run.
The time-slice for priority 0 should be 1 timer tick. The times-slice for priority 1 is 2 timer ticks; for priority 2, it is 4 timer ticks; for priority 3, it is 8 timer ticks.
When a timer tick occurs, whichever process was currently using the CPU should be considered to have used up a timer tick's worth of CPU. (Yes, a process could game the scheduler this way by relinquishing the CPU just before the timer tick occurs; ignore this!)
If a process wakes up after voluntarily relinquishing the CPU (by performing I/O or sleeping), it should be placed at the front of its queue; it should not preempt a process at the same priority.
Whenever a process is moved to a different priority level, it should be placed at the end of the corresponding queue.
A round-robin scheduler should be used for processes at the lowest priority.
There is no mechanism for the priority of a process to be raised again. (Yes, a process could starve and never recieve any CPU if higher-priority processes keep arriving; ignore this!)

graph1.pdf - shows how different process move down the queue over the time
graph2.pdf - shows I/O process which remain in the same priority for a long time as the relinquish the CPU before the              time slice expire, I/O process moves down the queue when run for a very long time
workload.pdf - Explaination of test cases & detailed explaination of the graphs
