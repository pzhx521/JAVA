### The Difference Between start() Method And run() Method

The **start() method is used to start threads**, which realizes multithreading.At this point, the thread is ready, **waiting for the CPU to schedule.** </br>

**The run() method is the thread body**, which contains the content of the thread to execute. When the thread enters the running state, it runs the code in the run() method.**When the run method terminates, the thread terminates.The whole invocation process is implemented by the bottom of jvm.** </br>

**If the run method is called directly, the operation is no different from calling a normal method and does not start multithreading.** </br>