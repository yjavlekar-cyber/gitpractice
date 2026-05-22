
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
6.git branch -m master main- to change local master name into man.
7.git remote add origin http- To connect remote to local.
8.git remote -v- To check the links are showing our not in local.
9.git remote set-url origin sshlink- to connect through ssh where it will not ask for username and all while pushing.

Origin-This is our remote repo which sometimes can be forked from company's code repo in order to be updated with the company code changes after forking once we cam add the upstream url and then directly pull from company source.
add upstream url -  git remote add upstream https://github.com/microsoft/vscode.git
 then
  git pull upstream main


DAY-3
git merge feature-signup- so basically you are in main branch and you are merging another branch called feature-signup into main.

fastforward- makes linear commit history.
commit merge- if the branch in which we are merging has gone forward with its commit history than fastforward is not possible hence git does commit merge where we can see visually two seprate commit history of two seprate branches


Remote (push, pull, fetch, clone, fork)
1.git push origin main- to push code from local to remote
2.git pull origin main - to pull from remote
3. git clone httpslink - to pull the repo from remote to local
4.forking is basically cloning but from github repo into our github.

Merge
1.git merge feature-login - to merge feature branch into main
2.git rebase main - to rebase the branch onto main branch or anyother branch.
3.git merge main --squash - to squash diff commits in one single commit we can use squash one squashed we will get the file in git status that we have to add and commit with new commit message.
4.git stash - to save the umcommited changes whil switching the branches
5.git stash pop- once we are back to the branch we can do git stash pop to get the file on which we are working.
6.git stash list - If there are are multiple stashes this will list the stashes.
7.git stash apply stash@{0}- To apply the specific stash from the stash list
8.git cherry-pick commit id- to cherry pick one particular commit from commit histroy.

Reset
git reset --soft HEAD~1 - to delete the last one commit.

-- soft = this deletes the commit.
-- mixed = This deletes the commit takes the file back to unstaged cateogry but keeps the file as it is
-- hard = Hard deletes all three the commit,gets file to unstaged and modifys the file to the stage before that particular deleted commit.

Revert
git revert commit id- to revert the commit.


