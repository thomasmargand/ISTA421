# Programming in C# Chapter 25 Homework
### Thomas Margand
### June 3, 2018

1. What is the purpose of the Universal Windows Platform? What was the name of the predecessor to
UWP?

The universal windows platform sought to combine the separate platforms that existed previously namely WinRT and Windows Phone SDK 8.0 (pg 601)

2. Describe in detail how the lifetime of a UWP app differs from a traditional desktop application.

The lifetime of a UWP app is somewhat different from that of a traditional desktop app. You should design apps that can run on devices such as smartphones to suspend execution when the user switches focus to another app and then to resume running when the focus returns. This approach can help to conserve resources and battery life on a constrained device. Windows might actually decide to close a suspended app if it determines that it needs to release system resources such as memory. When the app next runs, it should be able to resume where it left off. This means that you need to be prepared to manage app state information in your code, save it to hard disk, and restore it at the appropriate juncture. (pg 603)

3. Describe two ways you can set and modify the properties of controls.

You can either modify them from the property box on the right hand side of the solution explorer, or you can write the control properties into the XAML.

4. Describe the two layout schemes of UWP apps that we constructed in class.

As far as I can remember we have only ever used the 13.3 Desktop layout scheme to build UWP apps in class.

5. Describe three ways you can use the Visual State Manager to adapt the layout of UWP apps

You can create several versions of the MainPage.xaml file, you can use the Visual State Manager to modify the layout of the page a run time, or you can use the Visual State Manager to switch between views based on the height and width of the window. (pg 631)

6. Describe how you can modify multiple properties of multiple controls with one document. How do you
connect this modification document with your UWP application?

You can define a style and then call it on the desired page. 
