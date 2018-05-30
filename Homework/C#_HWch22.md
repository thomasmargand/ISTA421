# Programming in C# Chapter 22 Homework
### Thomas Margand
### May 23, 2018


1. Explain the difference between the concepts of associativity and precedence.

Associativity determines the direction in which an expression is evaluated right to left or left to right whereas precedence determines the order in which an expression is evaluated.

2. Explain the difference between the concepts of binary and unary operators.

A unary operator is an operator that has only one operand such as the increment operator.  A binary operator has two operands such as an addition operator.

3. List four constraints imposed by C# with respect to operator overloading.

You cannot change the precedence and associativity of an operator.
You cannot change the multiplicity of an operator.
You cannot invent new operator symbols.
You cannot change the meaning of operators when they are applied to built-in types.
(pg 494)

4. What is the syntax for overloading operators? Discuss access, scope, return value types, and parameter
types and multiplicity.

You use method like syntax with a return type and parameters, but the name of the method is the keyword *operator* together with the operator symbol you are declaring. The operator must be public and static. (pg 495)

5. What are symmetric overloaded binary operators and how do they differ from non-symmetric overloaded
binary operators?

If you overload the equality operator, you should also overload the inequality operator. Similarly, if you overload the less-than operator, you should also overload the greater-than operator.  The opposite of this would be a non-symmetric overload of a binary operator. (msdn) 

6. Can you overload compound assignment operators? If so, please state how you do so. If not, explain
why not.

Yes you can. If you have overloaded the appropriate simple operator, the overloaded version is automatically called when you use its associated compound assignment operator. (pg 498)

7. What is the difference between overloading increment and decrement operators for value types and
reference types?

Only the value types support the overloading of increment and decrement operators. This is because the syntax for overloading these operators would cause the original values to be decremented or incremented in the case of a reference type. Whereas when using a value type a new object is created and subsequently incremented or decremented leaving the original value unchanged, which is the desired outcome. (pg 500)

8. Why do we overload some operators in pairs?

Any operator that naturally comes in a pair such as the comparison or equation operators must both be explicitly defined.  Either neither or both. (pg 500)

9. What is the difference between widening conversion and narrowing conversion?

A widening conversion is an implicit conversion, called such because the result is wider than the original value and a narrowing conversion is an explicit conversion because the result is narrower than the original value. (pg 509)

10. What is the difference between explicit conversion and implicit conversion?

If a conversion is always safe, does not run the risk of losing information, and cannot throw an exception, it can be defined as an implicit conversion. Otherwise, it should be declared as an explicit conversion. (pg 510)
