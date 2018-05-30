# Programming in C# Chapter 23 Homework
### Thomas Margand
### May 23, 2018


1. List two reasons for multitasking, and explain the rationale for them.

To improve responsiveness by allowing multiple processes to take place at the same time and to improve scalability.  By allowing multiple operations to occur at once the application can do more within a given time frame and thus scale to something larger. (pg 518)

2. Explain Moore’s law. What does Moore’s law have to do with multitasking?

The number of transistors that can be placed inexpensively on an integrated circuit will increase exponentially, doubling every two years.  This law has held true for 50 years and lead to the rise of multicore processors as we have reached the physical limit for how fast an individual processor can be.  Multicore processors work by multitasking allowing a machine to do multiple things at once improving it's overall efficiency and speed. (pg 518)

3. In UWP, what namespace is used as the container for the multitasking methods?

`System.Threading.Tasks`

4. What is the difference between tasks and threads? Explain.

A task is something you want done. A thread is one of the many possible workers which performs that task.
https://stackoverflow.com/questions/4130194/what-is-the-difference-between-task-and-thread

5. What is the ThreadPool?

A queuing mechanism to distribute the workload across a set of threads allocated to a thread pool. (pg 520)

6. What parameters does the Task() constructor take?

All versions of the Task() constructor take an action delegate as the parameter. (pg 521)

7. How do you start a thread?

To create a new thread, you should leverage the ThreadStart delegate and pass the reference to a method that should execute on the thread. Note that a delegate is a type safe function pointer. The following code snippet shows you can create a new thread object using this delegate.

`Thread t = new Thread(new ThreadStart(MyThreadMethod));`

To start the newly created thread, you should call the Start method on the thread object you have created.
https://www.infoworld.com/article/3035134/application-development/how-to-work-with-threads-in-c.html

8. What is the difference between the Start() and Run() methods?

The Start() method adds a task to the threadpool to be scheduled.  When it is time for the task to be run the Run() method is called to execute it.

9. What is the difference between creating independent tasks with Tasks and parallelization with Parallel?
Explain.

Using the task class requires the explicit creation and implementation of tasks and when they are executed.  However, by using the parallel class the CLR can automatically optimize the creation, implementation, and execution of tasks generally allowing for more efficient use of processing resources.

10. Explain how manual cancellation works using a cancellation token.

A cancellation token is a structure that represents a request to cancel one or more tasks. If the application needs to cancel the tasks, it calls the cancel method of the CancellationTokenSource object. This method sets the IsCancellatonRequested property of the CancellationToken passed to all the tasks. (pg 543)
