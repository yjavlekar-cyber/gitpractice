
##SETUP AND CONFIG

---git --version- Tells what version of git is installed.

---git config --global user.name "Yogesh Jawlekar"-To set username for commit history.
---git config --global user.email "yjawlekar@gmel.com"-To set email of the username to list in commit history.


##BASIC WORKFLOW
---git init:Git init lets us intialize the local repo into a git repository to use it further to push or pull from remote repo.
---git add filename-lets us add the file into staging.
---git status-lets us check the status of the file if red then unstaged if green staged.
---git commit -m "commit message"-By this command we commit our changes into the git commit means basically keeping record of the changes.
Thats why git is called VCS (Version control system).
---git log/git log --oneline0- lets us check the commit history it shows the changes made earlier with details like who made those change which can be identified through username.


Above are the basic git commands one should know.

DAY-2 GIT COMMANDS BRANCHING-
1.git branch- to list down all the branches.
2.git branch newbranch- To create new branch.
3.git switch newbranch/git checkout newbranch- To switch into branch.
4.git checkout -b newbranch- To create new branch and switch it immedietly.
5.git branch -d(soft)/-D(hard) branchname- To delete branch.
6.
