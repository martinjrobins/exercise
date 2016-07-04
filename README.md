# Git Exercise

The following practical exercises should give you some familiarity with using 
Git. 

Note: The provided command line examples are to remind you of the correct syntax 
and keywords, and won't necessarily work if you type them in blindly

Other Note: to get help on a particular git command, use `git <command> --help`

## Setup
1. Install and setup git on your computer (remember to set your name/email)

~~~bash
$ git config --global user.name "Firstname Lastname"
$ git config --global user.email "example@maths.ox.ac.uk"
~~~

2. Create an account (or login) to GitHub at <https://github.com> 
3. (optional) Generate a ssh-key and add it to your GitHub account

~~~bash
$ ssh-keygen -t rsa -C "email@address.com"
$ cat ~/.ssh/id_rsa.pub
~~~

4. Fork this repository: <https://github.com/martinjrobins/exercise>

## Exercise 1: Making Commits

5. Clone the forked repository to your computer

~~~bash
$ git clone <url>
~~~

6. Create and add a new file

~~~bash
$ git add <file>
~~~

7. Edit the `Readme.md` file, then examine the state of your repo

~~~bash
$ git status
~~~

8. Commit everything you have done so far

~~~bash
$ git commit -a -m "message"
~~~

9. Make some more commits and view the log

~~~bash
$ git log 
~~~

10. Push the commits to the server

~~~bash
$ git push
~~~

## Exercise 2: Branching and Merging

1. Create a new branch 

~~~bash
$ git checkout -b new_branch
~~~

2. Edit the `Readme.md` file and commit the result
3. Swap back to the master branch

~~~bash
$ git checkout master
~~~

4. Merge `new_branch` to `master`

~~~bash
$ git merge new_branch
~~~

5. Now create conflicting commits in `new_branch` and `master` and try to merge 
   them. Note the conflict-resolution markers will look something like this.

~~~~~~bash
<<<<<<< HEAD
This is the new line in master
=======
This is the new line in branch
>>>>>>> branch
~~~~~~

6. resolve the conflict (i.e. edit the conflict markers to match how you want 
   the file to look like) and commit the result
7. Create some more commits to both `new_branch` and `master` and rebase 
   `new_branch` onto `master`. Remember that unlike the merge you did 
   previously, your HEAD should be on the branch you are rebasing (i.e 
   `new_branch`).

~~~bash
$ git rebase master
~~~


