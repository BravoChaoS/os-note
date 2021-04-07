# OS CH3: Process



## User space

### fork()

child process run the code **after** the fork()

### exec()

sometimes, the executed program will run *exit(0)* then the code after *exec(0)* won't run.

### wait() / waitpid()

cases:

1. suspend process and return (wake up) when:
   1. **one of its** child process changes **from running to terminated**
   2. receive a signal

2. return immediately
   1. it has no child

### fork() + exec() + wait()

let child process to run *exec()* , the parent process can resume.



## Kernel space

