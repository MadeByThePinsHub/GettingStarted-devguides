# Module 1.1: Meet Git

In Module 1.1, you'll learn today:
- the concepts of Version Control
- the introduction to Git
- the distributed Version Control

## Quick Video Talk

Recommended: Campus Advisor Training: Module 1.1 by GitHub Education on YouTube

<a href="http://www.youtube.com/watch?feature=player_embedded&v=uWsXEmaM3PA" target="_blank"><img src="http://img.youtube.com/vi/uWsXEmaM3PA/0.jpg" alt="Campus Advisor Training: Module 1.1" width="240" height="180" border="10" /></a>

## Interlude: Staging enviroment, commits and you ([from HotSpot Product & engineering Blog](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners))

One of the most confusing parts when you're first learning git is the concept of the staging environment and how it relates to a commit.

A [commit](git-scm.com/docs/git-commit) is a record of what files you have changed since the last time you made a commit. Essentially, you make changes to your repo (for example, adding a file or modifying one) and then tell git to put those files into a commit. Think of it as an checkpoint in a game, where you can return back when something goes wrong.
Commits make up the essence of your project and allow you to go back to the state of a project at any point.

"How I can tell Git which files put into a commit?", you asked. This is where the [**staging enviroment** or **index**](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) come in.
When you make changes to your repo, Git notices that a file has changed but won't do anything with it (like adding it in a commit).

To add a file to a commit, you first need to add it to the staging environment. To do this you can use `git add <filename>` command. ([see command docs for info](http://git-scm.com/docs/git-add))

Once you've used the git add command to add all the files you want to the staging environment, you can
then tell git to package them into a commit using the `git commit command`. ([see docs for help](http://git-scm.com/docs/git-commit))

> NOTE: The staging environment, also called 'staging', is the new preferred term for this, but you can also see it referred to as the 'index'.

## So, what is Git?
> Duck it, also see [the magic book for this](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F).

So, what is Git in a nutshell? This is an important section to absorb, because if you understand what Git is and the fundamentals of
how it works, then using Git effectively will probably be much easier for you. As you learn Git, try to clear your mind of the things
you may know about other VCSs, such as CVS, Subversion or Perforce — doing so will help you avoid subtle confusion when using the tool.
Even though Git’s user interface is fairly similar to these other VCSs, Git stores and thinks about information in a very different way,
and understanding these differences will help you avoid becoming confused while using it.

### Snapshots, not Diffs

### Nearly Every Operation Is Local

### Git Has Integrity

### Git Generally Only Adds Data

### Git Generally Only Adds Data
> We'll also learn about this on Module 1.2: 

## Post-Mortem: Your Module 1.1 Assignment

For a majority of your assignments you will create issues on GitHub.

In order to create an issue you will travel to the tab marked as `Issues`:

![](https://github.com/github-campus-advisors/Campus-Advisor-Training/blob/master/Module%201/assets/issue_one.png)

Once you click on that tab you will see all the current issues in this repository. At this point, no issues have been created. Let's create a new issue by clicking `New issue`

![](https://github.com/github-campus-advisors/Campus-Advisor-Training/blob/master/Module%201/assets/issue_two.png)

Once you have created a new issue, you will be greeted by the screen below. Here you will provide
* A title for your issue (Every title should be the name of the assignment, so in this case it is "Module 1.1 Assignment")
* A body for your issue to write a response or upload a screenshot
* A submission button

![](https://github.com/github-campus-advisors/Campus-Advisor-Training/blob/master/Module%201/assets/issue_three.png)

For the Module 1.1 Assignment copy the question below and paste it into the body of the issue and answer it:

`Given what you have learned about Git, why would you want to use Git in your classroom?`

Your issue body must contains like this below. This format will be used across all of the assignments within this course that require to use GitHub Issue Tracker.
```
Q: Given what you have learned about Git, why would you want to use Git in your classroom?

A: <your answer here>
```

> You'll also be prompted to make an reflection on what you learned on **Getting Started on Dev Guides - Module 1** after finishing all of the assignments.
> on [our original template repository](https://github.com/MadeByThePinsHub/GettingStarted-devguides/issues). Congratulations on your first assignment!
