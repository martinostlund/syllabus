## Examination assignment 2

In this assignment, we are going to implement a web-API following the theory of REST. We encourage you to have your own ideas about the API service to build. Maybe you have some idea you want to start with trough an API driven design? For those of you without any ideas, we will present a scenario below. That will also give a hint of the extent of this assignment.

## Overall requirements

We will emit obvious requirements like error handling, security, good code structure, accessible through HTTP/HTTPS, and so on. Of course, you will implement that without us telling you to! Below are some requirements for this assignment; either you choose your own implementation or use our suggestion. You are free to choose technical solutions like frameworks and modules for solving this assignment as long as the examiners could test your solution easily.

* The API should at least support representations with application/json
* The API should try to follow the constraints for Restful APIs
* The API should embrace the idea of HATEOAS. The API should have one entry point and use HATEOAS for making the API browsable.
* The API should give the client possibilities to create, read, update and delete resources.
* Unsafe HTTP methods and data about users in the system should require authentication done through the API with the implementation of JWT-tokens.
* The API should give some ability to register a webhook, which will trigger on some of you chosen event.
* In your examination repository, you should provide a [POSTMAN](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop) collection. The examiner should be able to load this into the POSTMAN application or a [NEWMAN CLI](https://www.getpostman.com/docs/postman/collection_runs/command_line_integration_with_newman) and test your API without any further configuration. For more information about POSTMAN and NEWMAN see this article: https://scotch.io/tutorials/write-api-tests-with-postman-and-newman
* Don't forget to make calls that show your error handling like bad requests, wrong credentials and so on.
* The code should be published in your examination repository along with a report (see below)
* Your solution should be testable without any configuration, installations of servers and so on. Preferable, the API will be testable through a public URL. Any instructions on how to test your solution should be in your repository README.md.
* The code should be individually created, the examiners may run a code anti-plagiarism tool on your code. Plagiarism will be reported.
* Make a script-file that automatically populated your application with some data for testing

## Our suggestion for those without own ideas

The fishing club "Den svartmunnade smörbultens banne" needs an API for collection fishing reports. They are thinking of building a client application but want a separate web API before taking this process along. The idea is that fishers should be able to report their catch and that this data could be made public. They want to collect data like:

* The user which catches the fish
* The position (longitude and latitude) of the catch
* Specie of the fish
* Weight
* Length
* Image-URL
* Timestamp of the catch

To do un-safe HTTP calls, the API must have  Authentication/Authorization. A user should be able to sign in through the API in a safe way (see requirements). 
Of course, you are free to implement further features in your web API.

## Report

This examination is a hand-in assignment. You will need to defend your design decisions in writing by answering the questions below in a report. This questions should be answered in your repository *RELEASE.md*. _(See details under "Hand in" below)_

The report should include the course code, course name, your name, and an introduction describing the problem you have tried to solve.

The following questions should be answered in the report.

1. Explain and defend your implementation of HATEOAS in your solution.
2. If your solution should implement multiple representations of the resources. How would you do it?
3. Motivate and defend your authentication solution. 
 1. What other authentication solutions could you implement?
 2. What pros/cons do this solution have?
4. Explain how your webhook works.
5. Since this is your first own web API, there are probably things you would solve in another way, looking back at this assignment. Write your thoughts about this.
6. Did you do something extra besides the fundamental requirements? Explain them.

## Examination

The grade for this assignment is F(fail), Fx(fail, with options to complement), and P(pass). We will take note of your effort and give you grades like P-, P, or P+ that could affect your final grade on this course. 
We will look at the structure of the API and the code, how easy your API is to understand, the extent of your effort, and the easiness for the examiner to test your solution.

### Hand in of the assignment

To hand in the assignment, you should finish a RELEASE.md-file in your project. Make sure you are in the root folder of your examination repository. Add the release-file by doing:
`wget https://gitlab.lnu.se/1dv527/content/examination-projects/release/raw/master/RELEASE.md`

Edit the file, and make sure you commit it and push it to GitLab.

## Tips

* Start by making a plan on how to solve the assignment. What do you have to do? What steps do you have to take? What do you need to know and learn? Plan your work!
* Start with your resources/models. Create them and write a seed-script that fill your storage with some data to play with when testing your API.
* Don't spend time on over-doing validation rules. In a real scenario, we should, but in this assignment, the API is the most important.
* Maybe a simple client application will help you to develop a good API, especially with respect to HATEOAS.
* Learning and using POSTMAN/Newman is your own responsibility. Make sure to read the article: https://scotch.io/tutorials/write-api-tests-with-postman-and-newman
