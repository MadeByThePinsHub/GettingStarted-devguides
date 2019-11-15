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
> Duck it, also see [the magic book for this](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F) where we borrowed it.

So, what is Git in a nutshell? This is an important section to absorb, because if you understand what Git is and the fundamentals of
how it works, then using Git effectively will probably be much easier for you. As you learn Git, try to clear your mind of the things
you may know about other VCSs, such as CVS, Subversion or Perforce — doing so will help you avoid subtle confusion when using the tool.
Even though Git’s user interface is fairly similar to these other VCSs, Git stores and thinks about information in a very different way,
and understanding these differences will help you avoid becoming confused while using it.

### Snapshots, not Diffs

The major difference between Git and any other VCS (Subversion and friends included) is the way Git thinks about its data. Conceptually, most other systems store information as a list of file-based changes. These other systems (CVS, Subversion, Perforce, Bazaar, and so on) think of the information they store as a set of files and the changes made to each file over time (this is commonly described as `delta-based` version control).

![](https://git-scm.com/book/en/v2/images/deltas.png)

Git doesn’t think of or store its data this way. Instead, Git thinks of its data more like a series of snapshots of a miniature filesystem. With Git, every time you commit, or save the state of your project, Git basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot. To be efficient, if files have not changed, Git doesn’t store the file again, just a link to the previous identical file it has already stored. Git thinks about its data more like a **stream of snapshots**.

![](https://git-scm.com/book/en/v2/images/snapshots.png)

This is an important distinction between Git and nearly all other VCSs. It makes Git reconsider almost every aspect of version control that most other systems copied from the previous generation. This makes Git more like a mini filesystem with some incredibly powerful tools built on top of it, rather than simply a VCS. We’ll explore some of the benefits you gain by thinking of your data this way when we cover Git branching in [Git Branching (in Pro Git Book)](https://git-scm.com/book/en/v2/ch00/ch03-git-branching).

### Nearly Every Operation Is Local

Most operations in Git need only local files and resources to operate — generally no information is needed from another computer on your network. If you’re used to a CVCS where most operations have that network latency overhead, this aspect of Git will make you think that the gods of speed have blessed Git with unworldly powers. Because you have the entire history of the project right there on your local disk, most operations seem almost instantaneous.

For example, to browse the history of the project, Git doesn’t need to go out to the server to get the history and display it for you — it simply reads it directly from your local database. This means you see the project history almost instantly. If you want to see the changes introduced between the current version of a file and the file a month ago, Git can look up the file a month ago and do a local difference calculation, instead of having to either ask a remote server to do it or pull an older version of the file from the remote server to do it locally.

This also means that there is very little you can’t do if you’re offline or off VPN. If you get on an airplane or a train and want to do a little work, you can commit happily (to your `local` copy, remember?) until you get to a network connection to upload. If you go home and can’t get your VPN client working properly, you can still work. In many other systems, doing so is either impossible or painful. In Perforce, for example, you can’t do much when you aren’t connected to the server; in Subversion and CVS, you can edit files, but you can’t commit changes to your database (because your database is offline). This may not seem like a huge deal, but you may be surprised what a big difference it can make. Ouch, right?

### Git Has Integrity

Everything in Git is checksummed before it is stored and is then referred to by that checksum. This means it’s impossible to change the contents of any file or directory without Git knowing about it. This functionality is built into Git at the lowest levels and is integral to its philosophy. You can’t lose information in transit or get file corruption without Git being able to detect it.

The mechanism that Git uses for this checksumming is called a SHA-1 hash. This is a 40-character string composed of hexadecimal characters (0–9 and a–f) and calculated based on the contents of a file or directory structure in Git. A SHA-1 hash looks something like `24b9da6552252987aa493b52f8696cd6d3b00373` or `450e2074753d65a7286c18ecc2ebb1ef734bb82c`.

You will see these hash values all over the place in Git because it uses them so much. In fact, Git stores everything in its database not by file name but by the hash value of its contents.

### Git Generally Only Adds Data

When you do actions in Git, nearly all of them only add data to the Git database. It is hard to get the system to do anything that is not undoable or to make it erase data in any way. As with any VCS, you can lose or mess up changes you haven’t committed yet, but after you commit a snapshot into Git, it is very difficult to lose, especially if you regularly push your database to another repository. (Unless you do some hard work there like making your own Git using from source.)

### The Three States
> We'll also learn about this on [Module 1.2: The Three State Model](./Module 1 - Git Basics/Module 1.2 - The Three State Model.md).


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
