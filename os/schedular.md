
## Type of work
- CPU Bound
- IO Bound

## Thread
### States
- Runnable:
- Waiting:
- Executing:

### Context switching
The physical act of swapping Threads on a core is called a context switch. A context switch happens when the scheduler pulls an Executing thread off a core and replaces it with a Runnable Thread. The Thread that was selected from the run queue moves into an Executing state. The Thread that was pulled can move back into a Runnable state (if it still has the ability to run), or into a Waiting state (if was replaced because of an IO-Bound type of request).

If your program is focused on CPU-Bound work, then context switches are going to be a performance nightmare. Since the Thead always has work to do, the context switch is stopping that work from progressing. This situation is in stark contrast with what happens with an IO-Bound workload

As an engineer, you needed to figure out how many Thread pools you needed and the max number of Threads for any given pool to maximize throughput for the number of cores that you were given. When it comes to using Thread pools to tune the performance of a service, it can get very complicated to find the right consistent configuration.