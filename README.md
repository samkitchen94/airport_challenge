Airport Challenge
=================

```
        ______
        _\____\___
=  = ==(____MA____)
          \_____\___________________,-~~~~~~~`-.._
          /     o o o o o o o o o o o o o o o o  |\_
          `~-.__       __..----..__                  )
                `---~~\___________/------------`````
                =  ===(_________)

```
# My Approach

I approached this task looking at each user story one at a time.

I then would run a feature test through IRB and assess what the program was/wasn't doing and add a unit test in to the appropriate spec file that would reflect what the particular function in the program is supposed to output. Then, I wrote the code that would make the test pass.

I have left a lot of the refactoring until the end which retrospectively was not the best idea! I will make a note not to do that next time.

Once I felt the user story was satisfied I have tried to add in more tests to defend against edge cases, although I have found getting the test coverage up to 95% very tough. I have found it hard to assess where the test coverage is lacking. Looking at the table the SimpleCov gem gives after running rspec, the files where 100% coverage is not shown all seem to be the gem files. I'm not sure if this is a mistake and it shouldn't be assessing test coverage for these files or whether I have missed something?

I have refactored methods so that they only perform one function and have tried to shorten tests to one line where possible. All tests have been organised against the method that they test against. Rubocop has been ran to make sure there are no mistakes in terms of formatting.

# How to Use
- From the parent directory load ./lib/airport.rb into irb.

- Create a new instance of a plane with Plane.new and create a new instance of an airport with Airport.new.

- Users can use the take_off method on remove a plane from the airport, and use the land method taking their instance of a plane to land the plane and store it at the airport.

- The airport can store 20 planes by default but this can be changed by the user.

- Planes cannot land if the airport is full, or if that instance of the plane has already landed.

- Planes cannot take off if that instance of a plane has already taken off.

- Planes cannot take off if it is stormy. There is a 1 in 5 chance of this happening, that has been enabled using a random number generator.


Instructions
---------

* Challenge time: rest of the day and weekend, until Monday 9am
* Feel free to use google, your notes, books, etc. but work on your own
* If you refer to the solution of another coach or student, please put a link to that in your README
* If you have a partial solution, **still check in a partial solution**
* You must submit a pull request to this repo with your code by 9am Monday morning

Steps
-------

1. Fork this repo, and clone to your local machine
2. Run the command `gem install bundle` (if you don't have bundle already)
3. When the installation completes, run `bundle`
4. Complete the following task:

Task
-----

We have a request from a client to write the software to control the flow of planes at an airport. The planes can land and take off provided that the weather is sunny. Occasionally it may be stormy, in which case no planes can land or take off.  Here are the user stories that we worked out in collaboration with the client:

```
As an air traffic controller
So I can get passengers to a destination
I want to instruct a plane to land at an airport

As an air traffic controller
So I can get passengers on the way to their destination
I want to instruct a plane to take off from an airport and confirm that it is no longer in the airport

As an air traffic controller
To ensure safety
I want to prevent takeoff when weather is stormy

As an air traffic controller
To ensure safety
I want to prevent landing when weather is stormy

As an air traffic controller
To ensure safety
I want to prevent landing when the airport is full

As the system designer
So that the software can be used for many different airports
I would like a default airport capacity that can be overridden as appropriate
```

Your task is to test drive the creation of a set of classes/modules to satisfy all the above user stories. You will need to use a random number generator to set the weather (it is normally sunny but on rare occasions it may be stormy). In your tests, you'll need to use a stub to override random weather to ensure consistent test behaviour.

Your code should defend against [edge cases](http://programmers.stackexchange.com/questions/125587/what-are-the-difference-between-an-edge-case-a-corner-case-a-base-case-and-a-b) such as inconsistent states of the system ensuring that planes can only take off from airports they are in; planes that are already flying cannot takes off and/or be in an airport; planes that are landed cannot land again and must be in an airport, etc.

For overriding random weather behaviour, please read the documentation to learn how to use test doubles: https://www.relishapp.com/rspec/rspec-mocks/docs . There’s an example of using a test double to test a die that’s relevant to testing random weather in the test.

Please create separate files for every class, module and test suite.

In code review we'll be hoping to see:

* All tests passing
* High [Test coverage](https://github.com/makersacademy/course/blob/master/pills/test_coverage.md) (>95% is good)
* The code is elegant: every class has a clear responsibility, methods are short etc.

Reviewers will potentially be using this [code review rubric](docs/review.md).  Referring to this rubric in advance will make the challenge somewhat easier.  You should be the judge of how much challenge you want this weekend.

**BONUS**

* Write an RSpec **feature** test that lands and takes off a number of planes

Note that is a practice 'tech test' of the kinds that employers use to screen developer applicants.  More detailed submission requirements/guidelines are in [CONTRIBUTING.md](CONTRIBUTING.md)

Finally, don’t overcomplicate things. This task isn’t as hard as it may seem at first.

* **Submit a pull request early.**  There are various checks that happen automatically when you send a pull request.  **Fix these issues if you can**.  Green is good.

* Finally, please submit a pull request before Monday at 9am with your solution or partial solution.  However much or little amount of code you wrote please please please submit a pull request before Monday at 9am.
