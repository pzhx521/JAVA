### The Life Cycle Of Threads 
When a thread is created, it does not go directly into the execution state, nor will it always be in the execution state.</br>
Therefore, in the lifecycle of a thread, it will experience five states: **New**, **Runnable**, **Running**, **Blocked** and **Dead**.</br>
These states are not strictly executed in sequence. According to the scheduling of the cpu, threads will continue to switch between these States until they die.</br>

1.The New state </br>
When a thread is created using the **new** keyword, the thread will be in a new state, at which time only **the JVM allocates memory for it and initializes its member variables.** </br>
eg:Thread thread = new Thread();

2.The Runnable state</br>
When the thread object calls the **start()** method, the thread is ready.**JVM will create its own method stack and program counter for the thread** and waits for CPU scheduling.</br>
eg:thread.start();

3.The Running state</br>
**When a thread in the Runnable state acquires the execution right of the cpu**, the thread will start executing the method body of the **run()** method, and the thread is in the running state.</br>

4.The Blocked state</br>
Blocked state refers to **the thread giving up the right to use the CPU for some reason**, that is, giving up its own CPU time slice and **temporarily stopping running.** </br>
There are three reasons for this.
*******
The first reason: Waiting for Blockage</br>
After the running thread executes the **wait()** method, **the JVM will put the thread in the waiting queue.** </br>
**wait()->waiting queue**
*******
The second reason:Synchronous blocking</br>
When a runtime thread **fails to acquire a synchronization lock for an object**, that is, the synchronization lock for that object is being occupied by another thread, **the JVM puts the thread into the lock pool.** </br>
**fails object lock->lock pool**
*******
The third reason:Other blockage</br>
When a running thread executes a **sleep()** method, **join()** method, or **makes an IO request**, the JVM sets the thread to a blocked state.**When the above operation times out or the processing ends, the thread can re-enter the runnable state.** </br>
**sleep()/join()/io request**
*******
5.The Dead state</br>
Threads end themselves in the following three ways, and the end is death.</br>
5.1 Normal end</br>
The **run()** method or **call()** method is executed, and the thread ends normally.</br>
5.2 Abnormal end</br>
**Thread throws an uncaught exception or error.** </br>
5.3 Call stop() method</br>
Call the stop() method of the thread directly, but **this method has been discarded.** </br>

The thread lifecycle state change diagram is as follows：
![life](https://github.com/pzhx521/JAVA/blob/master/concurrent/thread-2-1.PNG)
