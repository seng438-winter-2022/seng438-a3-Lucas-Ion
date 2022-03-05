**SENG 438 - Software Testing, Reliability, and Quality**

**Lab. Report #3 – Code Coverage, Adequacy Criteria and Test Case Correlation**

| Group \#: 33      |     |
| -------------- | --- |
| Student Names: |     |
| Lucas Ion               |     |
| Hao Nguyen               |     |
| Alden Lien               |     |
| Nguyen Gia Hy Huynh            |     |

(Note that some labs require individual reports while others require one report
for each group. Please see each lab document for details.)

# 1 Introduction

This assignment was similar to the previous assignment as in it aimed to test our unit testing knowledge and ability. For this assignment we utilized the EclipseIDE alongside EclEmma to perform Unit tests coupled with unit test coverage.

The primary underlying goal of this assignment was to give us an introduction to the concept of white-box testing approaches and to develop our skills in this domain. We manifested this development and growth through a variety of ways, firstly by understanding how to improve our code coverage, being able to effectively design test cases that improve code coverage, and being able to reflect on our newly designed test cases and what caused them to be effective. Moreover, this lab covered data flow diagram and data flow calculations, something that was critical to supplementing the white box testing approach.

# 2 Manual data-flow coverage calculations for X and Y methods

Text…

# 3 A detailed description of the testing strategy for the new unit test

Since the main goal of white-box testing is to cover the source code as comprehensively as possible, we used a different approach for our testing strategies in white-box testing.  Initially, our group needed to decide on what metrics we should use to guide ourselves with. Choosing the appropriate metrics for a specific requirement is essential for the early stage as it will decide quality and effectiveness of how our testing is formed. There are many options of testing metrics in white-box testing, however, we tried to stick to the instructions as much as possible so that we can achieve the metric for coverage, as layed out in assignment's requirement. Therefore, our group chose the three most popular metrics: statement (which was Line coverage in EclEmma), branch, and condition (which we replaced with Method in EclEmma).

The next step was to define the coverage level that we need to cover for each metrics. Following the documentation, we aim to achieve at least 80% branch coverage because branch coverage can be understood as the root of the other two methods. If we got the sufficient amount of coverage for branch, the others should be consistently high. Therefore our test development was designed with the goal of ensuring that every branch was met. When that was an "if statment", we always ensured that we wrote a case for if the "if statement" was not fulfilled irrespective of wheter or not there was an else statement. This ensured that we would maximize branch coverage. From our perspective as we increase branch coverage, method (condition) coverage and line (statement) coverage, would naturally increase.

At this point, requirement analysis has been settled which prompts us to next stage which is choosing the technology. We need to research on what technology should fit with our listed requirement. Again, the recommendation on assignment's documentation was really helpful, EclEmma is a nice coverage tool that supports branch, statement and condition (method) metrics. It also gives away rich coverage analysis where coverage results are highlighted and summarized that really intuitive to use.
  
In the implementation stage, we divided works fairly for each member and make the share is related to their previous work so that the implementation could be excuted smoothly. During the implementation process, we periodicaly checked up with each other so that people weren't stuck on a problem for too long or needed any help in understanding the current-testing method. After each test was written, we ensured our coverage result fullfilled our target requirement.

After all methods were  tested, we tried to recalibrate the suspected coverage result with manual calculations to make sure the result is concrete and could be presented to clients.

At the end, we cleaned up the testing by documenting and remove unneccesary testing methods

# 4 A high level description of five selected test cases you have designed using coverage information, and how they have increased code coverage

## ***Updated Test Cases***

**getCumulativePercentagesTest.java**

The method objective is to return a KeyedValues instance that contains the cumulativepercentage values for the data in another KeyedValues instance in the range from 0 to 1. My testing approach in this example is a hybrid of requirement-based testing and coverage based testing. Since the objective of this method is complicated and scientific, if I approach in one of the metrics as fully coverage-based testing, I will not totally ensure the efficiency and the accuracy of the test cases.

Thus, knowing that, I broke down the requirements in order to replicate the most efficient yet correct mocking data. Then I tried to minimize the possibility of angles that I should cover which ends up in two different parts: testing with valid values and with null values.

After that, the implementation is trivial. As the result, I was able to to achieve 100% coverage in all metrics statement, branch and condition, though, coverage-based was initially not mine intentive approach

**CalculateColumnTotalTest.java**

The method objective is to return the total of the values in one column of the supplied
The approach that I used to improve the coverage was branch-based coverage. In the older version, the black-box testing does not cover all possibilities came from if-else statement due to the difference in testing philosophy compared to white-box testing. When observing the problem at the branch metrics point of view, I managed to cover the unseen path and improve the coverage from ~85% to 100%. 

**expandTest.java**

The intended function of this method is to add margins to an existing range by taking three parameters. The first parameter is the given range, while the other two parameters are expressed as percentages of the range length and expand the lower or upper bounds respectively. 

The initial coverage on this method from Assignment 2 was 0%, as this method was not chosen to be tested. The strategy used to obtain coverage on this method and improve overall coverage of the Range.java class was to go for total statement coverage. However, after initial testing it was found that the conditional aspect of this method was not being covered in the unit tests. The solution implemented was to try and obtain complete branch coverage, by writing unit tests to test all potential branches of the control flow. This resulted in 100% statement and branch coverage of the method.

**TestExpandToInclude.java**

The method's objective is to change the given range to include the given value. My testing approach in this method is branch-based covering. Since this method has many different branches for different cases, I think this covering approach is the best way to improve the cover percentage of the method. By aiming to hit all the possible conditional branches with test cases, branch coverage rose greatly and all the other metrics followed with it. After this, implementation for each cases should be simple. With this approach, I managed to get 100% coverage in all metrics: statement and branch.

**equalTest.java**

The objective of the `equal` method is to test two arrays for equality. To be considered equal, the arrays must have exactly the same dimensions, and the values in each array must also match (two values that qre both NaN or both INF are considered equal in this test).

The requirement analysis for this method is trivial compared to the others methods in DataUtilities class. It is a comparision method between two arrays so it will be built up with mutiple if/else conditions. Therefore, our approach to cover this type of testing would be the branch metric. The Branch metric is a testing method that maximizes the coverage by testing all of the paths the program could reach when it is executed.

The next step of the implementation is to analyze the angles that should be covered to consistently achieve the coverage as well as the effectiveness of the suite case. 

After a careful analysis, we concludes that three test cases that should be written was injecting null values, arrays will different lengths, and valid values. For null-value injection, we test all the possibilities which includes either array is null and both are null. And the other two angles is straight-forward in terms of planning and implementing since there is not so much hidden path that we have to deep dive into. Note that when creating mocking data for all test cases, we tried to create as much objects as possible by reusing every cycle with the @After annotation in Unit Test.

As the result, the coverage percentage reaches 100% for all metrics as we primarily focus on the root metric.

# 5 A detailed report of the coverage achieved of each class and method (a screen shot from the code cover results in green and red color would suffice)

Text…

# 6 Pros and Cons of coverage tools used and Metrics you report

For this lab we decided to used EclEmma. As this was the tool that was recommended in the lab document.

## **Pros**

One of the very first benefits of using EclEmma is that it is a free to use tool. This means that the accesbility for code developing is not determined by the socio-economic standing of the developer themselves. This means that as many developers as possible can using a great and comprehensive tool for testing their code coverage, with the aim of doing testing.

Another benefit of EclEmma is that it uses colour coding alongside numeric values to convey coverage, this means that it becomes easier to undertsnaind and visualize how sucessful the various types of coverage may be.

EclEmma has excellent built in intergration with Eclipse, allowing it to easily be run using the play button, while subsequently providing stats in a very timely manner.

## **Cons**

One of the most glaring cons of EclEmma is that it can only be used with Eclipse, this means that the great functionality of EclEmma is limited to those who choose to opt for the Eclipse IDE versus other IDEs such as IntelliJ

Another con with EclEmma is that it is only compatible with the Java langauge, this means that the code testing coverage provided by EclEmma cannot by extension be provided to other languages such as Python or C++

One other con of EclEmma is that it does not given extensive reasoning for why the coverage was not fulfilled, with the due dilligence needing to be fulfilled by the tester themselves to investigate what it is that is actually causing the issues for the code. This can lead to significantly more investigation being needed.

# 7 A comparison on the advantages and disadvantages of requirements-based test generation and coverage-based test generation.

## **Requirement-based testing**

### ***Advantages:*** 

Requirement-based testing is a testing approach that focuses on covering the business requirement only and not wandering unnessary aspects. 

This approach is encouraged in Waterfall where work environment timely-managed and well-defined. The test design will be bounded within the definition of requirement, so it logically enhances the efficiency of each test suite. Since amount of test cases needed to be covered are lesser than other approach, the financial and time cost will also significantly decrease. Therefore, it is suitable for early stage developement where  resources are limited.

### ***Disadvanges:***

Due to its requirement-based characteristic, the quality of coverage unfortunately is under qualified in some cases. The test suite does not capture enough branches/paths and unexpected edge cases. Though it's good for Early stage development as its fast paced developement, the consequences of missing important test cases may highly cost the company in the next stages. 

## **Coverage-based testing**

### ***Advantages***

Coverage-based testing aims to achieve a high coverage result. By increasing the number of test cases, and focusing on testing different angles of the methods, this approach can ensure the quality of the program. With a high coverage, the program runs smoothly without worrying of any errors coming from the lines of code since they all have run through and tested. Also, the high quality testing can easily catch the attention of clients. There are various types of metrics for the coverage-based approach eg. statement, condition, branch, which gives multiple options for test designers to develop. 

### ***Disadvatages:***

With the high number of test cases being focused, high cost is an inevitable aspect when using this approach. It costs not only money and resources but also trades off the requirement-based focuses that might be more important. Although high coverage means codes has been fully tested, it does not mean that there will be no bugs at all when comes to the production stage. The number may not satisfied for the customers if it does not serve what they really want. 


## **Conclusion**

Each method has pros and cons. Requirements based testing can fulfill a time-boxed environment but this does not ensure the quality of the further product. Coverage based testing uses quantitative effects to ensure the qualitative aspect but is highly costly in pratical production. 

So when a software team chooses the testing method for their production, they must carefully define what is their primary focus for a specific stage. If in the Early stage, requirement-based testing could be recommended due to the fast-paced and low cost production, otherwise, coveraged-based testing can be worth to be considered.

# 8 A discussion on how the team work/effort was divided and managed

All team work was managed equally with everyone developing an equal number of test cases, as well as everyone contributing equally to the write up and manual calculations!

# 9 Any difficulties encountered, challenges overcome, and lessons learned from performing the lab

The first intial difficulty we faced was that the packages from Assignment 2 were not working correctly once imported to Assignment 3 as per the lab handout. However once we correctly modified the import statements to correspond to the correct location, everything worked well.

Another difficulty we had was that that initially EclEmma was not working correctly and was not installing correctly. Once we did an uninstall and reinstalled it from the Eclipse marketplace, everything functioned well!

# 10 Comments/feedback on the lab itself

We thoroughly enjoyed the lab as it allowed us to develop a more concrete understanding of white-box testing approaches. These apporaches coupled with interactive software really allowed us to grow our software engineering skills and to identify the key differences between the black-box and white-box testing approaches.
