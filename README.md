# Git Submodules 
Git can be used for dependency management as well.

## Things to know

### Git may not be the best tool in the tool box for this type of work
Depending on the programming language you are using there may be more robust options available.  For example, if you are using Java there is a tool called Maven that will help you manage dependencies with an extraordinary amount of flexibility.  These dependencies are specified in a file that is also used to configure all the phases of the software development cycle.  You can see an example in the Stata string utility library I created that makes use of this functionality [here](https://github.com/wbuchanan/StataStringUtilities).  More specifically, you'll want to view the [pom.xml](https://github.com/wbuchanan/StataStringUtilities/blob/master/pom.xml) file.

[R](https://cran.r-project.org), however, uses a fairly different format for dependency management.  You can see an example of what this looks like in an R project I have in CRAN and [GitHub](https://github.com/wbuchanan/regexPipes) to make it easier to use pipe operators with regular expressions:  [regexPipes](https://github.com/wbuchanan/regexPipes/blob/master/DESCRIPTION).

### Other times, Git may be the only tool
Other languages handle dependency management a bit differently.  In Stata, for example, code authors are expected to be a lot more aware of what their code depends on and to check/maintain things as needed.  Since one of the major conventions in the Stata community is to ruthlessly pursue backwards compatability (at least as much as possible) dependency management hasn't be a huge problem.


## What else are submodules good for?
One of the best features of using submodules is modularizing your code.  Sometimes you may want the same functionality to exist in multiple projects, but copying/pasting the same code in multiple locations means your maintenance workload grows extraordinarily quickly.  Submodules, on the other hand, allow you to break apart some functionality so it can be developed independently of the rest of the project.  If someone is working on an SQL function to return state test scores and someone else is working on a function to return National Student Clearinghouse data, you might both need demographic data.  Instead of developing additional code to query those demographic data, wouldn't it be nicer to use the same core queries for demographics that enforce common business rules across projects?  This is where the magic of submodules comes into play.

