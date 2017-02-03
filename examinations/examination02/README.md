## Examination assignment 2
In this assignment we are going to build a Restful web API. The idea is of course that you will use the theory in this course to build your own API. We encourage you to have your own ideas about the API to build. Maybe you have some kind of application idea you wan´t to start off with an API driven design. For those of you we will present a scenario to follow. That will also give a hint of the extent of this assignment.

## Overall requirements

We will emit obvious requirements like error handling, security and so on. Of course you will implement that without us telling you to! Below are some requirements for this assignment, either you choose your own implementation or use our suggestion.

* The API should be a web API meaning working through HTTP and/or HTTPS.
* The API should only support representations with application/json
* The API should follow the constraints for Restful APIs
* The API should embrace the idea of HATEOAS as good as possible.
* The API should be self-descriptive and easy to browse/explore
* The API should support CRUD operations where all data in the system should be available through API calls.
* Unsafe HTTP methods and data about users in the system should require some kind of authentication done through the API (you are free to choose implementation method for this).
* The API should give some ability to register a web hook which will trigger on some, of you chosen, event.
* In your examination repository you should provide a [POSTMAN](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop) collection. The examiner should be able to load this into the POSTMAN application and test your API without any further configuration.
* No visual UI needed (you are free to do if you want).
* We recommend writing your API in Node.js
* Of course - Answer the questions below

## Our suggestion for those without own ideas
The fishing club "Den svartmunnade smörbultens banne" needs an API for collection fishing reports and wants your help. They are thinking of building a client application but want a separated web API before taking this process along. The idea is that fishermen should be able to report their catch and that this data could be made public. They want data like:

* The user which catches the fish
* The position (longitude and latitude)
* Specie of the fish
* Weight
* Length
* image-url
* Timestamp
* Other information: like equipment, fishing method and so on
* A text describing the catch

To do un-safe HTTP calls the API must have some kind of Authentication/Authorization. A user should be able to sign in through the API in a safe way. You are free to choose your authentication strategy. This means that you also have to keep track of users in the system. When storing users you should store the common stuff like name, email, password etc.

Of course you are free to implement further feature you want in your web API.

## Questions
This examination is a hand-in assignment. You will need to defend your design decisions in writing by answering the below questions. This questions should be answered in your repository *README.md*.

1. How have you implemented the idea of HATEOAS in your API? Motivate your choices and how it support the idea of HATEOAS!
2. If your solution should implement multiple representations of the resources. How would you do it?
3. Motivate and defend your authentication solution? Why did you choose the one you did? Pros/Cons.
4. Explain how your web hook works.
5. Since this is your first own web API there are probably things you would solve in an other way looking back at this assignment. Write your thoughts down.
6. Did you do something extra besides the fundamental requirements? Explain them.

## Tips
* Start by making a plan how to solve the assignment. What do you have to do. What steps do you have to take. What do you need to know and learn? Plan your work! Use GitHUb or a other tool for this.
* Start with your resources/models. Create them and write a seed-script that fill your storage with some data to play with when testing your API.
* Don´t spend time on over-doing validation rules. In a real scenario we should but in this assignment the API is the most important.
