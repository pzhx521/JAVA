### Java Background Threads

Background threads, also known as **daemon threads** or service threads. </br>

It has a feature, that is, **it provides public services for user threads(main threads), and when there is no user threads, the background threads will automatically end.** </br>

The execution priority of daemon thread is lower.</br>

The **setDaemon(true)** method is used to set the thread as a daemon thread, but the setDaemon(true) method **must be used before the thread object is started (that is, before the start() method is called).** </br>

**New threads generated in daemon threads are also daemon's.** </br>

eg:
A garbage collector is a typical daemon thread that runs in the background and periodically performs certain tasks or waits for events to occur.When the garbage collector is the only thread left in the system, the garbage collector automatically ends.</br>
Automatic termination of daemon threads means the end of system operation.</br>
