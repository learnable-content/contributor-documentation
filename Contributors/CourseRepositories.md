#Course Repositories

We use GitHub to hold all our courses code samples. Each course is given its own repository. Branches are used to organise the contents of the course by lesson. The branch for each lesson includes that lesson's code samples, written content and handouts.

##Branches
Branches are organised per lesson/step and lesson stage. What this means is that every lesson/step in a course has its own branch. 

###Types of Branches
Branches are named after the course lessons. All lessons will have their own branch. They will contain starting code samples, written content and handouts.

If a lesson works through a code sample and has a final result that differs from the code used in the start of the lesson (because you've added to the code), that final result will be shown in its own branch. Why? So that we can put both branches side by side and compare the changes. We refer to these "results" branches as the "final branches". 

###Branch Naming Conventions
We know that we have two types of branches, the "lesson branch" per lesson in a course. We also have a "final branch" that shows the final result of a code example when the lesson has been completed. The naming conventions for these are slightly different:

**Lesson Branches** are named accordingly to their lesson. A branch made for lesson 2.1 in a course outline will be named: `lesson2.1`

**Final Branches** are named slightly different to the corresponding lesson branch. A branch with a final code result will be named like this: `lesson2.1final`

**_Why such particular naming rules?_**
Our system automatically picks up the branch names within a course and makes the corresponding repo content accessible within the site. It uses the naming convention as a keyword and is able to make the connection between the repo and course system. If repo branches are mis-named, the system may not be able to grab the resources for the lesson in question.

##Show Me Examples?

Sure thing, take a look at our jQuery course repository.
![jQuery course repo](Images/jQuery-course-repo.png)

When we look at the branches, we can see that we have `lesson1.1`, `lesson2.1`, `lesson2.1final` and so on. `lesson2.1final` is an example of a final branch.

![jQuery repo branches](Images/jQuery-repo-branches.png)

Now let's take a look at an actual branch. This is `lesson1.1`, you can see that it contains a couple of .md files of information. This is an .md version of a branch handout. Basically it caters as our written content, everything that is discussed/mentioned in the lesson.
![jQuery repo branches](Images/jQuery-branch-contents.png)
