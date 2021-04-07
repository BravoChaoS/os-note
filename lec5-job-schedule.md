# Job Schedule



- Context switching
- Scheduling
  - some basics
  - different algorithms
    - Shortest-job-first (SJF)
    - Round-robin (RR)
    - Priority scheduling with multiple queues
- Mordern Process with Threads
  - thread state
  - shared vs pre-thread state
  - thread lifecycle
- hyperthreading
- multiprocessing vs multiprogramming



## Context switching

- switching procedure, from one process to another

- when process change its status (ready <-> running <-> waiting), need context switching

- context switching is switching PCBs (process control block)



#### Cost

- direct cost: save & store, switching address space
- indirect cost: cache, TLB



## Scheduling

- Scheduling is required because the number of  computing resource –the CPU –is limited.

<img src="/home/jojjiw/Documents/os/os-note/lec5-job-schedule.assets/2021-03-17 15-31-46 的屏幕截图.png" alt="2021-03-17 15-31-46 的屏幕截图" style="zoom:67%;" />

### Scheduling algorithms

how to evaluate the algorithms?

- turnaround time: sum of all the process from arrival to terminated
- waiting time: sum of all the process from arrival to start running

#### Non-preemptive SJF

execute the process in the waiting list with **shortest CPU Require time**

#### Preemptive SJF

execute the process in the waiting list with **shortest CPU Remain time**

#### Round-robin

one by one

- give quantum to each process

- if all the quantum be used, will recharge for the processes


#### Priority Scheduling

<img src="/home/jojjiw/Documents/os/os-note/lec5-job-schedule.assets/2021-03-17 16-53-08 的屏幕截图.png" alt="2021-03-17 16-53-08 的屏幕截图" style="zoom:67%;" />

### Multiple queue priority scheduling

<img src="/home/jojjiw/Documents/os/os-note/lec5-job-schedule.assets/2021-03-24 14-16-48 的屏幕截图.png" alt="2021-03-24 14-16-48 的屏幕截图" style="zoom:80%;" />

Maybe this is the "multilevel ..." about Project1 Task3





