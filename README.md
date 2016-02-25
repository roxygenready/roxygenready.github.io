<!--# RoxygenReady
Prepare your R function library to be compiled into an R package by Roxygen-->
<!--      site under construction-->

## Create Roxygen skeletons for all of your functions before compiling it into an R package.


[**Roxygen2**](https://cran.r-project.org/web/packages/roxygen2/index.html) is an awesome tool to easily create a package from your function library. 

[**RoxygenReady**](https://github.com/vertesy/RoxygenReady) helps in creating the function annotations needed to compile a proper package by **Roxygen2**.

More precisely, **RoxygenReady** creates *Roxygen skeletons*, a certain format for inline function annotation (see below). By so, it spares you a lot of time documenting your functions easily and precisely. 

The annotation skeleton it creates, can be automatically compiled into a package with a few lines of code. Packages are the standard way of distribution R code, as they integrate with other services, code sharing becomes much easier. *See the installation section for an example.*

#### You can pass a whole file to **RoxygenReady**, and it will create *Roxygen skeletons* for all functions defined in the file!

<br><br>
## Workflow: *a streamlined package creation*

1. ### You start out with your .R file containing your favorite functions.

 		print11more <- function(n=1, m=1) { # a function with real added value
			print (n+(11*m))
		}

	- RoxygenReady expects a short description in the first line, after the `{` character, which will be parsed into the description field of the function annotation.


- ### Construct *Roxygen skeletons* RoxygenReady from all functions in your script.

		#' print11more
		#'
		#' # a function with real added value
		#' @param n
		#' @param m
		#' @examples print11more(n=1, m=1)
		#' @export


		print11more <- function(n=1, m=1) {
			print (n+(11*m))
		}


- ### Compile your package by roxygen.

	- See section: **How to create an R package?**


- ### Installing your package and share via GitHub!


       install.packages(RoxygenReady)
       require(RoxygenReady)

Browse for help on your functions `help(print11more)`:

![](https://raw.githubusercontent.com/vertesy/RoxygenReady/master/Images/03.b.Final.png)


You can share your package on **GitHub**, and everyone can super easily install it, like this package: read on!
	

<br><br>
## Installation

Install directly from **GitHub** via **devtools** with one R command:

<!--    devtools::install_github(repo = "vertesy/RoxygenReady/", subdir = "RoxygenReady")-->
    devtools::install_github(repo = "vertesy/RoxygenReady/RoxygenReady")
    
...then simply load the package:

    require("RoxygenReady")

<br><br>
## Package content

A couple of functions to generate inline description from your functions, using their names and arguments as default input. These can be later parsed by Roxygen to an R package's help section.

<br><br>
## How to create an R package?
> check: Workflow_to_Create_an_R_Package.R for details

1. Write or collect your favorite functions into an R script.
- **Prepare** in-line documentation **with RoxygenReady**
- Create a new package by **roxygen2**'s `create()` function, copy your functions script.
- Explain parameters in the in-line annotation; manually :-(
- **Compile** a package & documentation **by roxygen2**
- **Install** your package locally
- Test your package
- Share it with others via **GitHub**


<br>

      Check: Workflow_to_Create_an_R_Package.R for details

*Also check out a great introduction about writing your first package in R by [Hillary Parker](http://hilaryparker.com/2014/04/29/writing-an-r-package-from-scratch/)*


 <br/> <br/> <br/> <br/> <br/>
[*edit the website*](https://github.com/vertesy/RoxygenReady/generated_pages/new)