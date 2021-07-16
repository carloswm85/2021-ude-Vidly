# Vidly MVC Project

- Author: Carlos W. Mercado
- Date: July 16th, 2021.
- Course: https://www.udemy.com/course/the-complete-aspnet-mvc-5-course/

## Main Files Explanation
- **Model**: `\Models\Movie.cs` is a simple class, with properties and methods.
- **View**: `\Views\Movies\Random.cshtml` is a special HTML file, with C# content, it uses a template (or layout) from `\Views\Shared\_Layout.cshtml`, which contains all the necessary HTML code for the front-end. All the actual content for the page goes here.
- **Controller**: `\Controllers\MoviesController.cs` contains `class MoviesController : Controller { }` with `public ActionResult Random() { }` for returning the view, with the `Movie` object in it. This is `return View(movie);`