# Vidly MVC Project

- Author: Carlos W. Mercado
- Date: July 16th, 2021.
- Course: https://www.udemy.com/course/the-complete-aspnet-mvc-5-course/

## Main Files Explanation
- **Model**: `\Models\Movie.cs` is a simple class, with properties and methods.
- **View**: `\Views\Movies\Random.cshtml` is a special HTML file, with C# content, it uses a template (or layout) from `\Views\Shared\_Layout.cshtml`, which contains all the necessary HTML code for the front-end. All the actual content for the page goes here.
- **Controller**: `\Controllers\MoviesController.cs` contains `class MoviesController : Controller { }` with `public ActionResult Random() { }` for returning the view, with the `Movie` object in it. This is `return View(movie);`

## How to create a project in VS2019
- To create project like Mosh on VS 2019 you need to create project with  ASP.NET(.net framework) then when you will select MVC on right side click authentication and there chose 2nd option with single authentication log in (related to log in with FB etc.).

## Relevant Folder Locations and Files

Creating project structure:

- From VS2019 main window, select **"Start Window" button**.
- This will open **"What would you like to do?" window**;
  - Click "Create a new project" button
- **"Create a new project" window**:
  - Search for templates box (Alt + S): "mvc"
- Select **"ASP.NET Web Application (.NET Framework)" project type**, with keywords: C#, Windows, Cloud, Web. **NEXT**
- **"Configure a new project" window**:
  - Name your project: Main location for the app?
  - Select a location for the top-level folder. In my case, this location is the folder where I store all my Git repos.
  - Name your solution. As explained by VS2019 itself: "A solution is a container for one or more projets." This works as the repository name for me.
  - UNCHECKED: "Place solution and project in the same directory".
  - Selected framework: ".NET Framework 4.7.2"
- Press "Create" button. Then, **"Create a new ASP.NET Web Application"** window will open. Select "MVC". Then CHECK THEM ALL:
  - Select from "Authentication": "Individual User Accounts"
  - "Web Forms" option.
  - "MVC" option.
  - "Web API" option.
  - "Configure for HTTPS" option.
  - "Docker support" option.
  - "Also create a project for unit tests" option. The name is the same name than the project, but it can be changed.
- Press **"Create"** button. Project will be created, and you'll be taken to the main VS2019 window.
- You can now push the entire solution to your favorite repository hosting service.

This description is made from the _folder view_. Keep in mind that _solution view_ looks slightly different.

- `Packages` - (This one could be inside the main application folder.)
- `Vidly` - This is the `root` folder for the application.
  - `App_Data` - 
  - `App_Start` - 
    - `RouteConfig.cs → RegisterRoutes(RouteCollection routes)` - It routes any request made through the client, to a default controller with default values, or to client defined values.
  - `bin` - 
  - `Content` - CSS, images, client side assets.
  - `Controllers` - 3 controllers for default: Account (actions for sign up, log in, log out), Home, Manage (actions for handling requests around user's profile: changing password, enabling 2FA, using social logings, and so on).
  - `fonts` - It shouldn't be in the `root`, but preferibly in the `Content` folder
  - `Models` - All domain classes are here.
  - `obj` - 
  - `Properties` - 
  - `Scripts` - JS scripts are stored here.
  - `Views` - Folders named after controller in the application.
    - `Shared` - Views shared accross different controllers.
  - Other files at the `root` level:
    - `favicon.ico` - Icon of the application displayed in the browser's tab/window.
    - `Globals.asax` - Traditional file. It's a class that provides hooks for various events and applications life cycle (used to do that?). It is the file where you put the handlers for certain events as they have to be in a known class\location to be called.  Events like when Sessions and Applications start\end and so on (used to do that?).
    - `Globals.asax.cs` - 
      - `Application_Start()` - A few things are registered here. When the application starts, the runtime is told these are tor routes for our application.
    - `packages.config` - Used by Nuget package manager. It manages all the dependencies in the application.
    - `Startup.cs` - It's a new approach MS is taking for starting a application. It replaces _Global.asax_
    - `Vidly.csproj` - 
    - `Vidly.csproj.user` -
    - `Web.config` - It's an XML that includes the configuration for the application. The most important sections are `<connectionStrings>` (for database connection strings) and `<appSettings>` (for application configuration settings).
    - `Web.Debug.config` - 
    - `Web.Release.config` - 
    - `WebApp` - 
    - Docker files:
      - `.dockerignore` - 
      - `.Dockerfile` - 
- `Vidly.Tests` - 