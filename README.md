# Instructions for Code Test
## Objective
This is an example of a submitted solution to the first code test.  We would like to see how you go about debugging
someone elses code and what improvements you can find.  Submit a code review and bug report.  They do not have to be too
formal, something in markdown or a txt file is fine.  If you submit changed code please comment why you made the change.

## Submission
Add the code review / bug report as a file to the repository and push a branch up to origin, branch cannot be named
master.  Make a pull request once the branch is up on GitHub.

Below the line is the README.md that was submitted with the source code

---

# Overview
This was setup in two main pieces.  One to download and store the XML and the other to parse through the saved XML files.  My idea on how this would be run, for now, would be as a cron or some other scheduled task that would first download files and then parse through them.

In production I would expect this logic to be hit through some endpoint.  I have written the majority of the code in a way that would allow all the heavy logic to be flexible enough to be run in a few different ways with a small amount of code changes.

After looking over everything I suppose an argument could be made that this was 'over-engineered', so I have listed some reasons why I decided to write this code as I did.

* To make the code flexible I needed to make sure that there was as little hard-coding as possible in the logic.  I made the constants file as a way to seperate contextual information from the code.  One of my first changes would be to move this contextual data to config files and have a config parser setup the data for the program to run.  This allows greater flexibility when wanting to parse XML files differently based on config files alone.
* Writing some of the unit tests took longer than the code, but without them refactoring would be more difficult and take more time in the end.  Also I see the unittests as a way of documenting the expected behaviour of the program.  The unittests would need to be amended so that all functionality had positive and negative test cases as well as some edge cases caught.

## Instructions
#### Running Unittests
* Navigate to the root of the project
* To Run Tests :: ```python -m unittest discover -v```

#### Running Full Program
* From the project root :: ```python run.py```
* Navigate to the data directory to see the XML and related CSV
