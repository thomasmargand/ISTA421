MVC Lab Razor Tutorial
Thomas Margand
May 24, 2018


1. Access the command line and navigate to the directory where you store visual studio projects.
2. Type `dotnet new web -o mywebapp` and press enter. This creates a new web applications project titled mywebapp.
3. Open visual studio and open the mywebapp project.
4. Navigate to the startup.cs file and add the following to the ConfigureServices method;
   `services.AddMvc();`
5. Move down to the Configure method and add the following after the first if statement;
   `app.UseMvc();`
6. In the solution explorer add a new folder to the mywebapp project and title it Pages.
7. Move your mouse over the newly created pages folder in the solution explorer and right click then select add new item.
8. Add a razor page, the default name should be index.cshtml.
9. Navigate to the index.cshtml file, delete everything on the page and replace it with the following;
```
@page

<h1>Hello User, from the Header of a Razor Page</h1>
```
10. Mouse over the Pages folder again and add another Razor page, name it yourname.cshtml.
11. Navigate to the yourname.cshtml file, delete everything on the page and replace it with the following;
```
@page
<h1>Hi yourname</h1>

<p>This page is at /yourname</p>
<b>The concert starts at: @DateTime.Now  </b>
```
12. Save and build your application. Start without debugging.  The page should display Hello User, from the Header of a Razor Page, from the index.cshtml file.
13. Go to the address bar of your web browser and add /yourname then press enter. The content from the yourname.cshtml page should be displayed.
14. Close the browser.
