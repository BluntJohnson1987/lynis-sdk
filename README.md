# Lynis Software Development Kit

This project has three main goals:
* Provide tips to contributing the Lynis project
* Test the quality of the software
* Get you started with custom tests and plugins


## Getting Started

Development for Lynis is easy, as the tool is written in shell script. Although we use a few external tools, usually you don't need them.

Lynis uses the Bourne shell, usually /bin/sh on your system. Not to be confused with BASH (Bourne Again SHell). By adhering to the Bourne shell, the tool remains portable, and allows it to run on Linux, *BSD, Mac OSX, and others.

*Lesson: portability is important for the project. Every test should be running on different UNIX-derivatives as well.*

###

Go to the directory where you want to develop

cd my/dev/directory

Clone both projects:

```
git clone https://github.com/CISOfy/lynis
git clone https://github.com/CISOfy/lynis-sdk
```

Go to the SDK directory and run the development kit:

```
cd lynis-sdk
./lynis-devkit
```

This should give you screen output

With this kit you can perform quality checks, and test if everything works as expected. We encourage all developers and contributors to use this kit, especially before creating a pull request.



# Structure

Understanding the structure of the project is an important starting point

## Directories
In the tarball and on GitHub, you will see just a few directories.

### Root directory
The most important files, like the Lynis script itself, can be found in the root of the directory. It will include other things like the man page, documentation and changelog.

### Include directory
The directory is named "include", as more intelligence is included (or sourced) by the main script. This way it can import functions, initialize variables, and show the report. Also the individual tests are stored in this directory. They are grouped by category. This directory is definitely where most of the magic happens.

### Extra directory
Supporting documents and scripts are stored here.

# Style

Like any programming language, there are different ways to keep a project structured. It ranges from variable names, up to spacing. So we provide some guidelines to keep the structure and flexible enough for further expansion.

* Indentation is done with 4 spaces (no tabs)
* Variables are capitalized, optional with an underscore to "split" words


# Contribute

First step to contributing via GitHub, is by [forking](https://help.github.com/articles/fork-a-repo/) the project. This creates a local version for you to experiment.

* Fork it ( https://github.com/CISOfy/lynis/fork )
* Create your feature branch (git checkout -b adding-my-new-feature)

##  Making changes

Next step is making your local changes and test them.

**Tip:** To simplify testing, you don't have Lynis to perform all tests. Use --tests-category or --tests to specifically decide what tests to run.

After you are done, commit the changes: (git commit -am 'Adding some feature or improvement')

##  Testing

To improve the quality of your changes, tests should limit the amount of screen output. Important details should be logged to the log file, using the `logtext` function.

##  Send in your changes

Last step is creating a pull request. Provide a clear description on what the pull request is about (and why). If you have multiple changes to different tests, split them into multiple pull requests. This way it is easier to check and implement them in the master branch.

* Push to the branch (git push origin adding-my-new-feature)
* Create a new Pull Request

We perform regular linting on the code to keep.




## Directory Structure

lynis-devkit
Tool to perform a wide range of tests on the Lynis source.

LICENSE.MD
The GPLv3 license

README.MD
This file

docs/
This directory will host the most important pieces of documentation.

includes/  
unit-tests/
Components related to lynis-devkit
