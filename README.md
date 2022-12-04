# SASS---Customframework
A set of classes of SASS ready to use and customize (similar to Bulma)

## The approach of this "framework"
Before I started to create this framework, I realized that most of CSS frameworks are pretty heavy to download 
everytime you need to use them in your projects, so I decided to create a set of classes based on Bootstrap in 
order to give a solution for people to need a CSS intuitive and along with a nice visual aspect. 

---

# Get started
The framework consists in three main files with all the imports ans it's where the components are centralized.
To begin, the most important file of these three is `index.scss` at which the rest of files are use via `@use`.
With that said, you can able to modify, add or delete this templates by writting some code in this file.

### Requirements
To use this framework surely SASS and nodemon must be installed in your proyect or system, otherwise you won't 
be able to use the following commands.

### Development
When you're sure that your code is completed, you will want to build your SASS code to CSS for normal using. 
In the scripts of `package.json` are located the two scripts you need to use:

* `dev` watchs the `.scss` files inside your project, then it makes a build when you do changes or save the files.
* `build-css` as its name indicates, it builds the code for using. All the code built will live inside the `/css` folder, even also the code resulting of the `dev` script

### Testing
While you are typing some code in your SASS files, you probably want to see the changes, so something have to 
refresh the HTML page for you. If your IDE is VSCode you can use the extension "Live server" to refresh the changes
of the page. In case you don't want to use this extension, you can use whatever utility for refresing webpages.

Inside the `/test` folder you can put your debugging files, and all the stuff you consider necessary to use in your project.
By default, there's an example of the default classes in the framework which have essential classes for a simple webpage. 
In any case, don't forget you can set the styles of the framework as you want as follows.

---

# Internal engine
As I mentioned before, the performance inside this framework is quite a simple; how ever, if you want to get dived 
for more flexibilty at time of changing things, here you can approach it.

### Base
In the main level of the framework you will find a file called `_base.scss`, the most general settings of the styles
are written here. Nothing of styling here, you just must change the general *behaviour* of the styles, not the style 
itself. For instance, if you want to all the `h1` have a padding by default, it's properly to set that here instead of another file
that you will see in a few minutes. Or if you want set the `box-sizing` of all the elements to a different value, you can do
it here. 

> So that's the main purporse of that file: Changing the default behaviour in general of the elements of the page.

By default, the framework has some styles based in **Bootstrap** and **TailwindCSS**, so depending on your case, you can decide to change
this configurations:

```scss
*, *::after, *::before {
    box-sizing: border-box;
    padding: 0;
    margin: 0;
}

h1, h2, h3, h4, h5, h6, p{
    font-weight: normal;
}

a {
    text-decoration: none;
    display: block;
}

input, textarea {
    font-family: fonts.$font;
}
```

### Font family
As you can see in the above code, the `font-family` of the document is given by a variable of a module called `_fonts.scss`. By default, 
this framework has three font families imported from **Google fonts**:

 + **Lato** 
 + **Poppins**
 + **Roboto**
 
So you you cand import more font families from other urls or paths to use in your project. How ever, the default font family is `noto-sans` because
this framework was developed in *Linux*, so that is the common font family approched for this OS.

```scss
/* Lato, Poppins and Roboto respectively */
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&display=swap');

@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
```

In any case, if you want to change the font family because your approach is different, you will need to visit `/sass/variables/_fonts.scss` at which the default font family lives.

```scss
$font: "Noto Sans", "sans-serif";
```

---

# Utilities and helpers
The classes of the componenents and helpers are written in `/sass/*` folders and their names are inspired by *TailwindCSS* for the helpers, and 
the componenets are based on *Bootstrap* so that you can go to its Docs for more information about the componenets. 

### Components

In general, the componenets 
available are the following:

* Buttons
  * All the styles of *Bootstrap*
  * Button groups
    * All the desings and modes
* Card
  * Every style of the card
  * Card groups
    * Every type of card for its content
* Badges

> Be aware the components are performed by `@mixins` therefore this can be very helpful to you, because the code is only changed once.

### Utilities and API
There're a amount of mixins and variables you can modify inside `/mixins` and `/variables` folders. Then you can change the colors palette or theme. 

> For more information about colores and spacing go to `/variables/_colors.scss` and `/variables/_spacing.scss`.
> There're a whole palette with the most used colors in webpages inside `/sass/_colors.scss` so don't confund this file with the variables' file

Finally, all the helpers for a non-CSS page are in `/sass/helpers`, so can use them without writting those classes by your own:
* Displayment
* Flexbox
* Alignment
* Overflow
* Pointer events
* Positionments
* Spacing

---

> # Conclusion
> This project was performed in order to attach the concepts of **Markdown** and **SASS** by simuilating a real world approach. Since the full 
projects like this one displayed are pretty complex I didn't keep adding more feautures and classes, beacuse the main purporse if this project
was completed. How ever, this is a nice way to get dived in the creation of a framework; you're all the time thinking to write code as clean as 
possible for a better readbilty and usage.
> @Dadastudios
