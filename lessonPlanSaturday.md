# 16.1 & 16.2 Lesson Plan - Test Your Patience & Nightmare.js

### Overview

Today's lesson will introduce students to the basics of unit testing using Mocha and Chai, and acquaint them with the requirements of their second project.

#### Instructor Priorities

Students should be able to:

* Articulate the utility of unit tests;

* Incorporate Mocha and Chai into a Node project;

* Use Mocha to run unit tests written with Chai;

* Develop and submit a project proposal for instructor review.

#### Instructor Notes

* Please review [project notes](../../2-Homework/README.md) readme before class today!

* Remember&mdash;student projects are priority this week. Feel free to abbreviate today's lesson to accommodate project work.

* In the beginning of class, explain that, as this is project week, lesson plan material will only account for half the day's length.

  * For continuity's sake, explain that we'll cover testing material _first_, so students can focus on projects for the rest of the period.

* Have your TAs refer to the [Time Tracker](16.1-TimeTracker.xlsx) to stay on track.

- - -

### Class Objectives

Students should be able to:

* Recognize when unit tests are appropriate;

* Use Mocha and Chai to write tests against a given function;

* Describe a feature in terms of unit tests; and

* Develop and submit a project proposal for instructor review.

- - -

### 1. Instructor Do: Motivate Automated Testing (5 min.)

* Begin by asking different students how they make sure their code is working as expected.

* Many, if not most, will respond with various combinations of log statements and manually checking browser behavior.

* Point out that this is a time consuming and error-prone to test code. To the first point, taking the time to call functions and reload pages with different configurations can take up to a minute at a time. To the second, point out that it´s difficult to ensure you execute the same click sequences with the same settings in different configurations&mdash;e.g., checking behavior in Firefox vs Chrome.

* Explain that manual testing is useful in certain cases, but that it simply doesn't scale.

* Explain that tests are programs that automatically check the validity of your programs.

* Explain how this eliminates certain problems of scalability.

* Testing can feel unnatural at first. Reassure students that it becomes easier with practice.

* The more you get in the habit of writing test cases for basic functionality and corner cases, the easier breaking down algorithm/whiteboarding problems becomes.


### 6. Instructor Do: Mocha + Chai (5 min.)

* Explain that, just as jQuery provides utilities for manipulating the DOM, libraries like Mocha and Chai provide utilities for testing, such as `assertThrows`.

* Install Mocha and Chai.

  * To install Mocha: `npm i -g mocha`

  * To install Chai: `npm i -g chai`

  * If students prefer to install locally: `npm i -D chai`

* Write your own example of requiring and using Mocha and Chai, or simply walk through the provided `index.js` in [3-Mocha-Chai-Example/test/test.js](Activities/3-Mocha-Chai-Example/test/test.js).

* Explain the structure of a Mocha test suite. Focus on:

  * The `describe` clause;

  * The `it` clauses;

  * The phrasing of `should` clauses; and

  * Why we need an anonymous function to test if `multiply` throws. Don't spend undue time on this if students are obviously confused.

![Describe, it, and should clauses: Building blocks of good unit tests.](Images/5-mocha.png)

_Describe, it, and should clauses: Building blocks of good unit tests._

* Point out that this structure is intuitive enough so as to hardly require explanation beyond the `describe`/`it` structure.

* Point out that we described two characteristics of the `multiply` function. Explain that good tests will:

  1. test the behavior of a function on _representative examples_ of expected input; and

  2. Account for unexpected input.

### 7. Partners Do: Mocha + Chai Documentation, Testing disemvowel (15 min.)

* Slack out the links to the Mocha and Chai documentation.

* https://mochajs.org/ && http://chaijs.com/

* Slack out the following instructions:

* **Insructions**:

  * Familiarize yourself with the Mocha and Chai documentation. Choose to read either the should, expect, or assert guide, and refer to it throughout the exercise.

  * Consider a function, called `disemvowel`, which accepts a string and returns a version of the string without vowels.

  * Your task is to use Chai to write a test suite for `disemvowel`. The catch is that you don't get an implementation yet. First,

  * With your partner, determine what a "representative example" of an input to `disemvowel` might be.

  * What do we expect to receive? What should the function return of this input?

  * What different formats can this sort of input take?

  * What _don't_ we expect? What should happen in this case? _Hint_: Just come up with something reasonable. We're not going to make you guess how we handled errors, so you don't have to write a test for this.

  * When you think you're done, explain to your partner why the test you've written totally describes `disemvowel`. Be prepared to explain your test suite to the class.

### 8. Instructor Do: Review Activity (5 min.)

* Review the solution in [4-Disemvowel/Solved](Activities/4-Disemvowel/Solved/disemvowel.js).

* Explain each `it` clause.

* Encourage students to update their solutions to correspond to yours. This way, more of them will be motivated when their tests against `disemvowel.js` pass.

![it clauses in the disemvowel test.](Images/7-disemvowel.png)

_it clauses in the disemvowel test._

* Explain that the purpose of this exercise is to learn to write tests that describe a _what_ a function does without worrying about _how_ it does it.

* This is a powerful concept. It allows us to write tests _before_ we write implementations, thus providing us with checks that our program behaves as expected that we can incrementally satisfy as we actually implement it.

* Slack out the file `disemvowel.js`, and encourage students to run their tests against it. Explain that the solution is intentionally cryptic, to drive home the point that writing tests can be done independently of considering implementations.

* Hopefully, several groups will enjoy passing tests against a function they've never seen.

![Passing tests for disemvowel.](Images/7-disemvowel-passing-tests.png)

_Passing tests for disemvowel._


-----


### Overview

In this class, we will be introducing students to the principles of user stories and of functional testing using Nightmare.js.

#### Instructor Priorities

* Students should be able to articulate the differences between functional and unit testing.

* Students should understand how to integrate Nightmare.js into a Node project.

* Students should be able to draft basic user stories to describe common pathways through their applications and to use Nightmare to verify that their application behaves properly in these circumstances.

#### Instructor Notes

* If you haven't already, please review [project notes](../../2-Homework/README.md) before class today.

* Remember that student projects are the priority this week. Feel free to abbreviate this lesson plan by skipping or shortening activities as you see fit.

* Testing is largely a thing of habit. As such, today's lesson will largely consist of activities. Once you've given an overview of Nightmare's API, give students the bulk of class to practice.

* The goal for today is specifically to get students comfortable with drafting user stories and with implementing them with Nightmare. They are free to write tests against arbitrary websites to do so.

* Have your TAs refer to the [16.2 TimeTracker](16.2-TimeTracker.xlsx) to stay on task.

- - -

### Class Objectives

* To gain initial exposure to functional testing in JavaScript.

* To gain initial exposure to Nightmare.js.

* To use Nightmare to verify a website's behavior.

- - -

### 1. Instructor Do: User Stories & Nightmare (5 mins)

* Ask a student to explain what unit tests are and what they're used for.

* Ask several students if they can think of any shortcomings of unit tests.

* Point out that while unit tests guarantee that our functions work properly, they don't necessarily guarantee that they coordinate properly.

* Explain that the purpose of _functional_ tests is to ensure that these units work properly in combination by verifying that particular _features_ of an application work properly.

  * Point out that a feature&mdash;such as saving user data&mdash;requires many _units_ to function.

  * Emphasize that good unit tests typically verify only _individual units_ of functionality.

  * Explain that since features involve the coordination of many such units, functional testing demands a different approach.

      ![What functions are involved here?](Images/1-interactive-chart.png)
      _Ask students how testing a visualization like this might be different from testing the functions that produce the data._

* Explain that functional tests verify whether features work as the user expects. Unit tests verify that the logic works as the programmer expects.

* Explain that functional tests are generally written in terms of the user's expectations of a feature. Some examples include the following:

  * Google allows users to enter a search term, and then directs them to a page with search results.

  * Facebook allows users to like something a friend shared, and then displays how many users have liked that item.

  * Dropbox allows users to drag files to the browser, and then uploads that file to a database.

* Explain that such functionality, expressed briefly in a sentence or two, constitutes a _user story_.

  * These often follow a template: as a _user_, I want to &lt;_action_> so I can &lt;_reason_>.

* Give a few examples:

  * As a user, I want to send tweets so others can read them.

  * As an Android user, I want to be able to search for apps by name and to sort them by rating.

  * As a Node developer, I want to be able to easily download code others have written so I can develop more quickly.

    * Explain that user stories of this magnitude would be broken down into a series of smaller ones.

* Tell students that just as there are libraries such as Chai that ease unit testing, there are libraries that ease functional testing.

* Slack out the Nightmare.js GitHub page: <https://github.com/segmentio/nightmare>

* Explain that Nightmare effectively launches a browser and interacts with it as if it were a user.

* Quickly run the example script from the Nightmare page. This is copied for convenience in [1-Nightmare-Example](Activities/1-Nightmare-Example).

    ![Important Nightmare methods.](Images/1-nightmare-example.png)
    _Important Nightmare methods._


* Explain what happened, and briefly explain a few of Nightmare's methods. If time allows, ask a few students to name some common browser interactions. See if there are any Nightmare methods that correspond to them.

* Alternatively, mention that some of the most commonly used are the following:

  * `goto(url)`: Navigate to `url`.

  * `click(selector)`: Click the element represented by `selector`.

  * `back()`: Navigate to the previous page.


-----



### 2. Students Do: Browser Automation with Nightmare (15 mins)

* Tell students to create a new NPM project.

* Install Nightmare locally: `npm install --save-dev nightmare` or `npm i -D nightmare`.

* Slack out the following instructions:

  * **Instructions**

    * Refer to the Nightmare documentation here: <https://github.com/segmentio/nightmare#api>

    * Choose a site with which you're familiar. Write a few user stories for it.

    * Using the Nightmare documentation, try to implement a few of your user stories.

    * Take a look at the `screenshot` and `html` methods. Try to use them. Can you think of any use cases for these methods?

    * Be prepared to share your user stories with the class.

    * _Hint_: If you have trouble interacting with elements you expect to be on the page, try using `wait`. Don't forget to use your browser's dev tools to determine the correct element selectors!

-----


### 3. Instructor Do: Review Activity (5 mins)

* Ask a few students to share their user stories.

* Refer to the example in [2-Browser-Automation/Solved](Activities/2-Browser-Automation/Solved). Use one you created beforehand, or live-code one similar to the provided example.

    ![Important methods in the Codecademy demonstration. Use the screenshots to demonstrate the flow.](Images/3-nightmare-solution.png)

    _Important methods in the Codecademy demonstration. Use the screenshots to demonstrate the flow._

* Walk through the logic.


* Take some time to answer student questions.


### 5. Instructor Do: Nightmare & Mocha Review (5 mins)

* Point out that we can use Nightmare to automate browsers this way but that we'll generally want a report on whether the application behaved as expected.

* Explain that we can use Nightmare in conjunction with Mocha to encapsulate our user stories in `describe` and `it` clauses and to generate test reports akin to those we get when unit testing.

* Open up [3-Nightmare-Tests-Example](Activities/3-Nightmare-Tests-Example), run the tests, and briefly explain the output.

* Break one of the tests, and demonstrate how this changes the test report.

    ![Nightmare's test output should look pretty familiar.](Images/5-nightmare-test-output.png)
    _Nightmare's test output should look pretty familiar._


* Ask a few groups to explain their user stories.

* Return to the example in [3-Nightmare-Tests-Example](Activities/3-Nightmare-Tests-Example).

  * Explain the implementation, but don't belabor it. Rather, focus on the logic behind choosing these tests.

  * Explain that the tests, taken together, verify a primary subset of the site's core functionality. In other words, they _specify_ how this feature should work.

* Point out the relationship between functional tests and specifications.

* Explain that it's good practice to write tests _before_ writing your implementations.

  * Even if you change your tests after writing the application code, writing these tests beforehand helps clarify the application's functionality.

  * Tests provide you with a verification layer to ensure that you're on the right track as you develop.

  * A test suite notifies you when you introduce bugs while working on new, potentially unrelated features in the future.

* Answer any questions about the Nightmare API, user stories, and tests in general. Encourage students to write at least a few tests for every project on which they work, and gradually work towards writing tests for every feature.

  * Emphasize that this is an ideal. Students shouldn't feel obligated to test _everything_. Rather, they should aim to write tests regularly.

### 8. END

- - -

