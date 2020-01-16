When your Go program starts up, it’s given a Logical Processor (P) for every virtual core.

Under Hyper-Threading mechanisim,
Virtual Core = (Physical Core) * (Hardware Thread per Physical core)

Every P is assigned an OS Thread (“M”). The ‘M’ stands for machine. This Thread is still managed by the OS.
Every Go program is also given an initial Goroutine (“G”), which is the path of execution for a Go program. You can think of Goroutines as application-level threads and they are similar to OS Threads in many ways. Just as OS Threads are context-switched on and off a core, Goroutines are context-switched on and off an M.

There are two different run queues in the Go scheduler: the Global Run Queue (GRQ) and the Local Run Queue (LRQ).

## Context Switching
The Go scheduler requires well-defined user-space events that occur at safe points in the code to context-switch from. 

## Conclusion
The Go scheduler is really amazing in how the design takes into account the intricacies of how the OS and the hardware work. The ability to turn IO/Blocking work into CPU-bound work at the OS level is where we get a big win in leveraging more CPU capacity over time. 