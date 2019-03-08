### The Difference Between sleep() Method And wait() Method

1.The **sleep()** method belongs to the **Thread** class, while the **wait()** method belongs to the **Object** class.</br>

2.Calls to **sleep() and wait()** methods can cause threads **to become blocked.** </br>

3.During the **sleep()** method call, the thread only temporarily abandons the right to use the cpu, and automatically restores to the ready state after the specified time of sleep, waiting for execution.**Threads do not release object locks during this period.** </br>

4.During the **wait()** method call, **the thread will abandon the object lock and enter the waiting lock pool of the object.** Only when the object calls the **notify()** method, the thread leaves the lock pool and enters the ready state and waits for execution.</br>