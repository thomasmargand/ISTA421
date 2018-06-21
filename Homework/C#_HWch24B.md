# Programming in C# Chapter 24B Homework
### Thomas Margand
### May 25, 2018

1. What are the two scenarios in which you can use PLINQ to speed up operations? Why does using
PLINQ in these scenarios speed up processing?

PLINQ is ideal for scenarios that involve data sets with large numbers of elements, or if the criteria specified for matching data involve, complex, computationally expensive operations. (pg 575)

2. How does AsParallel qualify as an extension method? First, explain what an extension method is and
how you define extension methods, and them explain why AsParallel qualifies as an extension method.

Extension methods enable you to "add" methods to existing types without creating a new derived type, recompiling, or otherwise modifying the original type. Extension methods are a special kind of static method, but they are called as if they were instance methods on the extended type. The most common extension methods are the LINQ standard query operators that add query functionality to the existing System.Collections.IEnumerable and System.Collections.Generic.IEnumerable<T> types. To use the standard query operators, first bring them into scope with a using System.Linq directive. Then any type that implements IEnumerable<T> appears to have instance methods such as GroupBy, OrderBy, Average, and so on.

https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/extension-methods
https://docs.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2010/bb383977(v=vs.100)

3. How do you cancel a PLINQ query before it finishes? Be specific with respect to the variables and
methods used for the cancellation operation, and how the variables and methods are used.

You can cancel a PLINQ query by specifying a CancellationToken object from a CancellationTokenSource and use the WithCancellation extension method of the ParallelQuery. (pg 580)

4. Why is it important to synchronize concurrent access to a server? Give an example of a specific
condition that will cause an error in your application if concurrent access is not synchronized.

If two tasks attempt to access and modify the same data. If both tasks run at the same time, their overlapping operations might corrupt the data.  This situation can lead to bugs that are difficult to correct, primarily because of their unpredictability. (pg 581)

5. What does the lock statement do?

You can use the lock keyword to guarantee exclusive access to resources. (pg 584)

6. This is not in the book. Define mutex, define semaphore, and explain the difference between them.

The mutex class is a synchronization primitive that can also be used for interprocess synchronization. A semaphore class limits the number of threads that can access a resource or pool of resources concurrently.

https://msdn.microsoft.com/en-us/library/system.threading.mutex%28v=vs.110%29.aspx?f=255&MSPPError=-2147217396
https://msdn.microsoft.com/en-us/library/system.threading.semaphore(v=vs.110).aspx

7. What does it mean to say that some collection classes are not thread safe? Explain how not being
thread safe may lead one of these collection classes to produce a malfunction in the program.

A code is called thread safe if it is being called from multiple threads concurrently without the breaking of functionalities.  A collection that is not thread safe could cause corruptions of data.

https://www.c-sharpcorner.com/UploadFile/1c8574/thread-safety369/

8. Explain how thread safe collection classes are made thread safe.

Multiple threads can safely and efficiently add or remove items from these collections, without requiring additional synchronization in user code.
https://docs.microsoft.com/en-us/dotnet/standard/collections/thread-safe/

9. Why are thread safe classes slower than non-thread safe classes? Be specific.

Some of the concurrent collection types use lightweight synchronization mechanisms such as SpinLock, SpinWait, SemaphoreSlim, and CountdownEvent, which are new in the .NET Framework 4. These synchronization types typically use busy spinning for brief periods before they put the thread into a true Wait state. When wait times are expected to be very short, spinning is far less computationally expensive than waiting, which involves an expensive kernel transition. For collection classes that use spinning, this efficiency means that multiple threads can add and remove items at a very high rate. For more information about spinning vs. blocking, see SpinLock and SpinWait. The ConcurrentQueue<T> and ConcurrentStack<T> classes do not use locks at all. Instead, they rely on Interlocked operations to achieve thread-safety.

https://docs.microsoft.com/en-us/dotnet/standard/collections/thread-safe/
