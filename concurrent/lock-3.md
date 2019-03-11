### Synchronized

The synchronize keyword **can lock any non-null object.** It belongs to **the exclusive pessimistic lock and the re-entrainable lock.** </br>

Scope of synchronized Keyword:</br>
1.When it acts as a **common method,the current object instance (this) is locked.** </br>
2.When it acts as a **static method,the class instance is locked.** </br>
3.When it acts on a **non-null object,it latches all blocks of code that are locked on that object.** </br>
eg:
```java
public class Test{

	//1
	public synchronized void test1(){
		//do something
	}

	//2
	public static synchronized void test2(){
		//do something
	}
	
	//3
	public void test3(){
		synchronized("object"){
			//do something
		}
	}
}
```
*******
Core components of synchronized keyword：
1.wait set: </br>
Wait for the collection, **call the wait() method, and place the blocked thread here.** </br>
2.contention List: </br>
Competition list in which **all threads requesting locks are first placed.** </br>
3.entry List:</br>
**Threads eligible to be candidates in the contention list are moved into the entry list.** </br>
4.ondeck:</br>
**At any time, at most one thread is competing for a resource lock, which becomes ondeck.** </br>
5.owner:</br>
**Threads that currently have access to lock resources are called owner.** </br>
6.!owner:</br>
**Threads that release current lock resources are called !owner.** </br>
*******








