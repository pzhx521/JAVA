### Spin Lock

The principle of spin lock: If the thread holding the lock can release the resource in a very short time, it can let the thread waiting for the resource enter the spin state, so that it has enough time to wait for the thread holding the lock to release the lock, thus avoiding the blocking state due to acquiring the lock, and avoiding the switching consumption of user thread and kernel. </br>

**Thread spin consumes CPU**. In short, **it makes the CPU do idle work.** If the lock can not be acquired all the time, the thread will always occupy the CPU to do idle work, **so it needs to set a maximum time of spin waiting.** If the spin waiting time is exceeded, the thread will **stop spinning and enter blocking state.** </br>

Advantages and disadvantages of spin lock:</br>

For code blocks where lock competition is not intense and lock time is very short, spinning can bring about a significant performance improvement. </br>

If the competition for locks is fierce, or the thread holding locks takes a long time to occupy the lock execution synchronization block, then spin locks will always occupy the CPU for idle work, resulting in a waste of CPU resources.At this point, the consumption of thread spin will be greater than that of thread blocking pending operation.</br>
*******
Spin lock time threshold:</br>

In order to prevent spin lock from occupying CPU resources for a long time, it is very important to select the spin time period.</br>

In **jdk1.5**, the limit time of spinlock is **written to death.** </br>

In **jdk1.6**, **an adaptive spin lock** is introduced. At this time, the spin time is **not fixed**, but determined by the previous spin time on the same lock and the state of the lock owner. At the same time, the JVM also decides whether to stop the spin according to the current load of the cpu.The -XX:+UseSpinning parameter opens adaptive spin lock.</br>

Since **jdk1.7**, this parameter has been removed and **controlled by JVM to achieve the best results.** </br>
