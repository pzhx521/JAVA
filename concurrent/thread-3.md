### Four Ways To Terminate Threads 

1.The first way</br>
When the **run()** method or **call()** method runs out, the thread automatically ends.</br>

2.The second way</br>
When a thread needs to run until certain external conditions are met, it is not closed.You can **use a variable to control the loop.** </br>
Code example:
```java
public class MyThread extends Thread{
	
	/*
	 *The variable is modified with volatile keyword, 
	 *which guarantees the visibility of the variable among multiple threads. 
	 *That is to say, when another thread modifies the variable, 
	 *the thread immediately sees the result of the modification.
	 *
	/
	public volatile boolean exitFalg = false;
	
	@Override 
	public void run(){
		while(exitFalg){
			//do something
		}
	}
}
```

3.The third way</br>
Using the **interrupt()** method to interrupt threads, there are two situations in this way.</br>
*******
3.1
When a thread is blocked, when the thread's **interrupt()** method is called, the thread **throws an InterceptorException** exception.By capturing the exception, you can use the **return** jump method or **break** jump out of the loop to end the thread.</br>
```java
public class MyThread extends Thread{
	
	@Override
	public void run(){
		
		while(true){
			try{
				Thread.sleep(1000);
				//do something ...
			}catch(InterceptorException e){
				e.printStackTrace();
				break;//or return;
			}
		}
	}
}
```
*******
3.2
When the thread is not blocked, the **isInterrupted()** method can be used to determine whether the thread has been interrupted.This principle is the same as the mark bit control cycle.</br>
```java
public class MyThread extends Thread{
	
	@Override
	public void run(){
		
		while(!isInterrupted()){
			//do something ...
		}
	}
}
```
*******
3.3
The **stop()** method is used, but **it is unsafe and has been abandoned.** </br>
*******