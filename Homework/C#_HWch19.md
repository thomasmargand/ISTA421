# Programming in C# Chapter 19 Homework
### Thomas Margand
### April 25, 2018

1. What is an enumerable collection?

A collection that implements the System.Collections.IEnumerable interface. (pg 423)

2. What properties and methods does the IEnumerable interface contain?

The IEnumerable interface contains a single method called GetEnumerator.
`IEnumerator GetEnumerator();` (pg 424)

3. What properties and methods does the IEnumerator interface contain?

```
object Current { get; }
bool MoveNext();
void Reset();
```
It has one property and two methods see above. (pg 424)

4. What values does the MoveNext() method return? What does it do?

The MoveNext() method returns a boolean and moves the pointer down the line to the next item in the list; the MoveNext method should return true if there actually is another item and false if there isn't. (pg 424)

5. What values does the Reset() method return? What does it do?

The Reset method returns the pointer back to before the first item in the list, the method is void so it does not return a value. (pg 424)

6. Are IEnumerable and IEnumerator type safe? Why or why not? If not, how do you implement type
safety?

They are not type safe they return objects rather than a specific type, however the .NET Framework contains interfaces in the System.Collections.Generic namespace that are type space and is recommended that you use these generic interfaces rather than the non-generic versions. (pg 424)

7. Why don’t recursive methods retain state when used with data structures like binary trees?

The recursive method being called starts fresh every time that is calls itself.  The point at which the method calls itself is before a return value is reached, because nothing is returned there are no other state values to be maintained.

8. How do you define an enumerator?

Think of an enumerator as a pointer indicating elements in a list.

9. What is an iterator?

An iterator is a block of code that yields an ordered sequence of values. (pg 431)

10. What does yield do?

The yield keyword indicates the value that should be returned by each iteration.  (pg 432)

**Exercise 9 help**
hash a string...use md5? String.GetHash Method()
get user input...place it in an array?
compare strings
