### Multithread Implementation And Creation
1.Extends <u style="color:#7DABDC"> **java.lang.Thread** </u>
The **Thread** class essentially implements <u style="color:#7DABDC">java.lang.Runnable</u> interface, and an object of this class represent an instance of thread. **The only way to start the thread is to call the <font color="#7DABDC">start()</font> method.** </br>
Of course, the **start()** method is a <u> native method </u> that will start a new thread and execute its own **<font color="#7DABDC">run()</font>** method.</br>

```java
public class MyThread extends Thread{
	
	@Override
	public void run(){
		//Business logic ...
	}
}

//start thread
MyThread thread=new MyThread();
thread.start();

```
