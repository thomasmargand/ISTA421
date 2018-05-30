# Programming in C# Chapter 21 Homework
### Thomas Margand
### May 10, 2018


1. What is the difference in the purposes of SQL and LINQ? In other words, why do we need two different
query languages? Does LINQ replace SQL? Does SQL make LINQ unnecessary?

SQL works exclusively with SQL databases, whereas LINQ can be incorporated into many other programming languages.  SQL does not provide a means to change underlying data structures or the method in which queries are done instead leaving that up to the database management system. However LINQ is more flexible and allows for control.

2. What is the one essential requirement for the data structures used with LINQ? Why is this requirement
important?

The data structures must use the IEnumerable or IEnumerable<T> interface. (pg 471)

3. Where does the LINQ Select() method live?

It is an extension method of the Enumerable class.  The Enumerable class is located in the System.Linq namespace and provides a substantial set of static methods for querying objects that implement the generic IEnumerable<T> interface. (pg 473)

4. (Select) Explain, token by token, each token in this line of code:
`IEnumerable<string> customerFirstNames = customers.Select(cust => cust.FirstName);`

First the IEnumerable interface is called to create a string object named customerFirstNames and that variable is set equal to the first names from the customers table using the Select method of LINQ.

5. (Filter) Explain, token by token, each token in this line of code:
`IEnumerable<string> usCompanies = addresses.Where(addr =>
String.Equals(addr.Country, "United States")).Select(usComp => usComp.CompanyName);`

This does something similar to the previous one except it returns all the company names from companies in the United States.

6. (OrderBy) Explain, token by token, each token in this line of code:
`IEnumerable<string> companyNames = addresses.OrderBy(addr =>
addr.CompanyName).Select(comp => comp.CompanyName);`

This returns a list of all company names ordered by address.

7. (Group) Explain, token by token, each token in this line of code:
`var companiesGroupedByCountry = addresses.GroupBy(addrs => addrs.Country);`

This returns a list of all the companies grouped by address.

8. (Distinct) Explain, token by token, each token in this line of code:
`int numberOfCountries = addresses.Select(addr => addr.Country).Distinct().Count();`

This company returns and integer representing all the distinct countries in the address table.

9. (Join) Explain, token by token, each token in this line of code:
```
var companiesAndCustomers =
  customers.Select(c =>
      new { c.FirstName, c.LastName, c.CompanyName }).Join(addresses, custs =>
      custs.CompanyName, addrs => addrs.CompanyName, (custs, addrs) =>
      new {custs.FirstName, custs.LastName, addrs.Country });
      ```

This joins tables and returns a list of each company's customer's first and last names.

10. Explain the difference between a deferred collection and a static, cached collection.

A deferred collection defers evaluation as last so any changes made to the collection prior to iterating through it will be reflected.  However in a cached collection a local copy is made and will not change if the original collection is changed. 
