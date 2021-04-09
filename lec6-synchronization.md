

# Inter-process Communication (IPC)

## IPC

- signal
- shared object
  - pipe
  - fifo
  - semaphore
- message passing



## Race condition

Race condition: the **outcome** of an execution **depends on** a particular **order** in which the shared resource is accessed.

- To control the **entry and exit** of critical section



## Critical section

code segment that access shared objects

- **it should be as tight as possible**



## Entry and Exit implementation

requirements:

- Mutual Exclusion
- Bounded Waiting
- Progress

### Mutual Exclusion

No two processes could be simultaneously go inside their own critical sections.

- Lock-based
  - Spin-based lock
  - Sleep-based lock
- Lock-free

### Bounded Waiting

One a process starts trying to enter her CS, the waiting time is bounded.

### Progress

Always at least one process can enter CS.



### Spin-based lock

1. turn = 0/1, two process take turns
2. turn = 0/1, intrested[0/1] = True/False. intrested shows whether there is a CS requirement of process

### Sleep-based lock

semaphore / pThread_mutex_lock



## Classic IPC problem

- Producer-consumer problem.
- Dining philosopher problem.

### Producer-consumer problem

#### requirement

1. Mutual exclusion

   - While you are eating, people cannot steal your chopstick

   - Two persons cannot hold the same chopstick

2. Synchronization

   - Should avoid **deadlock**.
   - should avoid **starvation**: Philosophers are all busy (no deadlock), but no progress

#### solution

- chopsticks are semaphore -> philosophers are semaphore
- mutex: 保证原子操作
- p[i]: semaphore, philosopher i 的两根筷子

<img src="lec6-synchronization.assets/2021-04-07 14-34-24 的屏幕截图.png" alt="2021-04-07 14-34-24 的屏幕截图" style="zoom:80%;" />
