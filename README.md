# DevOpsCourse
This Repo is used for DevOps Course, Exercise 4: Git

Q1: Why do we use Git?
Git is a Version Control System (VCS). We use it to easily track every change in source code. It is also used for coordinating work among programmers collaboratively developing source code during software development. Its goals include speed, data integrity, and support for distributed, non-linear workflows


Q2: What is repository? Which files should have a good repository?
A Git repository is the .git/ folder inside a project. This repository tracks all changes made to files in your project, building a history over time. In other words, a git repository is a container for source code.
A good repository must have 3 file:
Readme.md
Licence
.gitignore


Q3: which parts should have a professional document?
A professional document should have 3 main parts as described below:
1. Explain the project goals and exactly what it does. 
2. Explain how to use it (install, config, run, delete,...) by providing 
3. Explain how other people can collaborate


Q4: what does the "git clone" command do?
Clone a repository into a new directory


Q5: which command do you use to update your local repository with origin?
git pull


Q6: what is the difference between revert, reset and checkout?
git revert
This command creates a new commit that undoes the changes from a previous commit. This command adds new history to the project (it doesn't modify existing history).

git checkout
This command checks-out content from the repository and puts it in your work tree. It can also have other effects, depending on how the command was invoked. For instance, it can also change which branch you are currently working on. This command doesn't make any changes to the history.

git reset
This command is a little more complicated. It actually does a couple of different things depending on how it is invoked. It modifies the index (the so-called "staging area"). Or it changes which commit a branch head is currently pointing at. This command may alter existing history (by changing the commit that a branch references).


Q7: what is the difference between merge and release?
Git rebase and merge both integrate changes from one branch into another. Where they differ is how it's done. Git rebase moves a feature branch into a master. Git merge adds a new commit, preserving the history.



Q8: which command do you use for revealing the commands history?
git log


Q9: which command do you use to track changes within one specific file?
git diff 


Q10: what is a tag used for? and how can create a tag?
Git has the ability to tag specific points in a repository’s history as being important. Typically, people use this functionality to mark release points (v1.0, v2.0 and so on). 
Git supports two types of tags: lightweight and annotated. A lightweight tag is very much like a branch that doesn’t change — it’s just a pointer to a specific commit. Annotated tags, however, are stored as full objects in the Git database. They’re checksummed; contain the tagger name, email, and date; have a tagging message; and can be signed and verified with GNU Privacy Guard (GPG). It’s generally recommended that you create annotated tags so you can have all this information; but if you want a temporary tag or for some reason don’t want to keep the other information, lightweight tags are available too.

Create lightweight tag:
git tag <tag label>

Example: 
Git tag v1.7

Create annotated tag:
Git tag -a <tag label>  -m <massage>

Example:
Git tag -a v1.7 -m “version 1.7”

  
Q11: how can you use git to collaborate on a project?
First of all I should create a local repository on my local computer system according below:

mkdir my-project
cd my-project
git init 

then I should clone the project from origin into master by:

git clone  <remote repository address>

(if you clone from a private repository make sure you set your ssh key config at remote repository or every other configs that you may need to do before cloning the code.)


Q12: why do you use branches? and how can you merge them?
Git branches are effectively a pointer to a snapshot of your changes. When you want to add a new feature or fix a bug—no matter how big or how small—you spawn a new branch to encapsulate your changes. This makes it harder for unstable code to get merged into the main code base, and it gives you the chance to clean up your future's history before merging it into the main branch.
If you have a branch named fix-bug and want to merge it with master branch, you can use these commands:

Git checkout master
Git merge fix-bug

Consider that above commands add a new commit to your project history, if you want to merge without adding a new commit, you can use rebase but be cautious while using it:
  
Git checkout master
Git rebase master fix-bug

