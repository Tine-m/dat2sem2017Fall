# Testing workshop
Denne note er på engelsk da den er delvis genbrugt fra tidligere

## Monday November 27th.

As preparation for Monday, you should view the following on Lynda:
<https://www.lynda.com/Developer-Programming-Foundations-tutorials/Welcome/124398/137955-4.html>. 
It is nearly two hours, so remember to set some time aside.

There are a few sections which can be skipped:

- There is a section on how to do it in Eclipse - we use Netbeans, so that is different for us.
- Section 5 "Additional topics" can be skipped


### Plan

#### Basic unit tests (green level)
1. Designing for test ([slides](TestSlides.pptx))
1. Quiz
3. Exercise: Make a number of tests for a method that computes the number of rafters (spær) based on length of a carport. Make the the method to compute it, and make it pass all the tests.

#### Database testing (yellow level)
Mostly it is not recommended to test the actual database layer. 
However, that is a shame as many get the database layer wrong. Once the structure is in place, it is fairly straight forward to do.

Reading:

- This [note by Lasse Koskela](databaseTest.md) explains the principle of how to seperate the connection object from the actual database facade.

1. Testing the database layer
	- Test database vs. production database
	- Clearing and setting up a database
	- Designing for testability
	- A dedicated connection
	
2. [Unit testing against MySQL](IntegrationstestDatabase.md)


## A few other concepts of test
7. Aspects of test ([slides](TestSlides.pptx))
	- (green level) Testing can be more than JUnit (acceptance test, system tests,...)
	- (green level)Testing concept: Black and White box test
	- (Red level) Testing concept: Test coverrage
9. Red level: Install [codecoverage in jacocoverage](Codecoverage in Netbeans.md) and check coverage of your test for quicksort.

	
	
