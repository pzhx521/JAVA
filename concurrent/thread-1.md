### Multithread Implementation And Creation
1.Inheritance Class **java.lang.Thread** </br>
The **Thread** class essentially implements **java.lang.Runnable** interface, and an object of this class represent an instance of thread. **The only way to start the thread is to call the start() method.** </br>
Of course, the **start()** method is a native method that will start a new thread and execute its own **run()** method.</br>

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

2.Implementing **java.lang.Runnable** Interface </br>
This approach is recommended.

```java
public class MyThread implements Runnable{

	@Override
	public void run(){
		//Business logic
	}
}
//start thread
Thread thread = new Thread(new MyThread());
thread.start();

```

