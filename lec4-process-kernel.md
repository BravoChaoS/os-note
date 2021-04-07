# Process kernel

## user time VS sys time

## fork()

## exec()

## wait() & exit()

### **wait()**

1. blocks the parent

### **exit()**

1. clean up **most of** the allocated kernel-space memory (parent will clean up the rest of things)
2. clean up exit process's user-space memory
3. Notify the parent with SIGCHILD

### **wait()**

2. receive and handling the child process (delete all of the child process)
3. return child PID

### overall

- exit after wait

<img src="/home/jojjiw/Documents/os/os-note/lec4-process-kernel.assets/2021-03-17 14-27-00 的屏幕截图.png" alt="2021-03-17 14-27-00 的屏幕截图" style="zoom: 67%;" />

- exit before wait

<img src="/home/jojjiw/Documents/os/os-note/lec4-process-kernel.assets/2021-03-17 14-37-32 的屏幕截图.png" alt="2021-03-17 14-37-32 的屏幕截图" style="zoom:67%;" />



## Process blossoming

### The init process

- PID = 1
- program code in /sbin/init

### Process tree

- command: pstree
- <img src="/home/jojjiw/Documents/os/os-note/lec4-process-kernel.assets/2021-03-17 14-44-53 的屏幕截图.png" alt="2021-03-17 14-44-53 的屏幕截图" style="zoom:67%;" />

### Re-parent

- to handling the situation if the parent process need to be killed but child process still need running
- child process re-parent to init process (in Linux)

#### process of re-parent

1. parent process call exit()
2. clean up and notify [see process of **exit()**]
3. list of child of init process **append** the pid of child process
4. child process **change** parent pid to 1(init process)



## Process lifecycle

<img src="/home/jojjiw/Documents/os/os-note/lec4-process-kernel.assets/2021-03-17 15-02-32 的屏幕截图.png" alt="2021-03-17 15-02-32 的屏幕截图" style="zoom:67%;" />

> Ignore the white block

### Fork()

- other process create this process (except init)

### Three state: Ready Running and Waiting

#### Ready

- ready to run but is not running

- a process in ready queue when be killed, ready -> running -> zombie / terminated

#### Running

- a running process

#### Waiting /  Blocked

- only running process can wait / be blocked
- there are interruptible and un-interruptible states

#### Zombie

- terminate it self
- force to be terminated