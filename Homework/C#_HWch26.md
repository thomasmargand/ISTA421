# Programming in C# Chapter 26 Homework
### Thomas Margand
### June 5, 2018

1. Describe the three concerns that the Model-View-ViewModel design pattern addresses.

It helps to remove dependencies between the various components, enabling different presentations of the data without needing to change the business logic or the underlying data model. This allows for different elements to be designed and implemented by individuals who have the appropriate and specialist skills. (pg 652)

2. Describe in detail how the MVVM design pattern works.

In this design pattern, the model provides the data used by the app, and the view represents the way in which the data is displayed in the UI. The ViewModel contains the logic that connects the two, taking the user input and converting it into commands that perform business operations on the model, and also taking the data from the model and formatting it in the manner expected by the view. (pg 652)

3. Describe in detail how data binding works with respect to controls and models.

Using data binding, you can link a property of a control to a property of an object; if the value of the specified property of the object changes, the property in the control that is linked to the object also changes. (pg 652)

4. Describe the three methods that the ICommand interface defines. What is the purpose of each method?

CanExecute - This method returns a boolean value indicating whether the command can run.
Execute - This method runs when the command is invoked.
CanExecuteChanged - This event is triggered when the state of the ViewModel changes. (pg 670)

5. What is a data context? Why do we need a data context? What does it do?

Data context is a property that must be set so that the same data binding automatically applies to all the controls on the form. (pg 656)
