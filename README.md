# CS259 Coursework Template File
This repository contains a Gradle project designed to serve as a starting point template for the University of Warwick CS259 Formal Languages coursework (as of 2020).

## Details
* Gradle Version: 6.2.2
* JavaCC Gradle plugin details [here.](https://github.com/IntershopCommunicationsAG/javacc-gradle-plugin).
* JavaCC details and documentation [here.](https://github.com/javacc/javacc)
* Unit testing framework: [JUnit 4.](https://junit.org/junit4/)

Note: Version 4 of the JavaCC plugin will only work with Gradle 6 and JDK 8.
## Directory Structure
* `src/main/javacc` - Contains the javacc for the parser (Assignment.jj).
* `src/main/java` - Contains the Java classes produced from Assignment.jj.
* `src/main/resources` - Contains `input.txt` and `error.txt`. The parser reads the contents of `input.txt` and places the contents of StdError in `error.txt`. These files are used when running `gradle run` and are not affected by running `gradle test`.
* `src/test/java` - Contains `AssignmentTest.java` JUnit tests.
* `src/test/resources` - Contains individual test files, `solutions.txt` containing reasons for rejected programs, and `tests.json`, which stores for each test file the expected results of running the parser on that file.

## Adding tests.

You can add your own test cases in the JUnit test file (`src/test/java/AssignmentTest.java`) explicity, or include another test file to be ran as a text file under `src/test/java/resources`. If you include a test file you need to add the expected outcome to `tests.json` so that the output of your parser can be validated.

## Build commands
`gradle run`: Run the parser with `input.txt` as input. Standard Out is printed to console, Standard Error printed to `error.txt`

`gradle build`: Run `javacc` and compile resulting java source code

`gradle javacc`: Run `javacc` to produce Java source code from Assignment.jj

`gradle test`: Run the unit tests.

## Before you submit...
Be sure to check the parser in an isolated environment without any package or Gradle dependencies, as listed in the assignment brief. This means you need to remove the `package PLMParser` at the top of the file and re-build the java source code. Submitting the JavaCC file with the `package` line at the top of the file won't pass automated testing as you cant just `java` run it like a normal .class file.


