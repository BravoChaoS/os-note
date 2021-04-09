# Deadlock

## Starvation VS Deadlock

### Starvation

thread waits indefinitely

- Low-priority thread waiting for resources constantly in use by high-priority threads

### Deadlock

circular waiting for resources

### Compare

Deadlock -> Starvation, but not vice versa

- Starvation can end (but does not have to)
- Deadlock cannot end without external intervention



## Conditions

### All of four conditions should be satisfied

<img src="lec7-deadlock.assets/image-20210407153610954.png" alt="image-20210407153610954" style="zoom:80%;" />

### ==Cycle != Deadlock==

![image-2021040715365393](lec7-deadlock.assets/image-20210407153653932.png)
