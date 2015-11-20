# Basic Git and Github info

### General workflow
``` sh   
# Do this often during the work session
$ git pull # get the latest version of the repo
$ git add -A # add all to repo
$ git commit -m "message"
# First generate SSH key on your local machine, add it to Github account.
# https://help.github.com/articles/generating-ssh-keys
$ git remote set-url origin git@github.com:yourUsername/yourReponame.git
```

### No more username & password input for every push
``` sh   
# First generate SSH key on your local machine, add it to Github account.
# https://help.github.com/articles/generating-ssh-keys
$ git remote set-url origin git@github.com:yourUsername/yourReponame.git
```

### Creating a repository online for the <b>1st time</b>!
``` sh
# navigated into your folder you want to put on Github
$ git init # initialize your git repository locally
$ git add . # adds everything changed from local to staging
$ git commit -m "first commit" # commit to local git repo
$ git remote add origin https://github.com/quinnliu/GitCommands.git
$ git push origin master # push repo to Github
# put in a username & password
```

### When adding on to your repository online with changes
``` sh
$ git add .
$ git add -u # use if you deleted a local file and it needs to be removed from the repo
$ git commit -m 'what has changed'
$ git push
# put in username & password
```

### Working on repo you made through github or with somebody elses repo
``` sh
# fork repo you want to work on
$ git clone https://github.com/yourUsername/reponame.git
$ git status # show the difference between local repo and repo on Github
$ git pull # use this after someone else made a change to the online repo
           # get local repo up to date on changes
```

### Branch Commands
``` sh
$ git pull # in master branch get the latest version of the repo
# creating a new branch
$ git branch # show the current branch
$ git branch -a # list all branches in working folder  
$ git branch newBranchName # creates a new branch, copies code from current branch
$ git checkout newBranchName # switch to branch newBranchName
# makes changes to the code
$ git add -A
$ git commit -m "message"

# pull request to push to Github and have your code reviewed
$ git checkout master # make sure your local master branch is the same as Github master branch
$ git pull
# if Github master branch is different that your local master branch
$ git checkout newBranchName #go back to your branch
$ git merge master #merge new updates of master with newBranchName branch
$ git add -A
$ git commit
$ git push  # push newBranchName up to Github

#in Github
# create pull request
# when your code is approved, that person will Merge pull request
# your branch will be merged with master branch

# merging new branch to old branch
$ git checkout oldBranchName
$ git merge --no-ff newBranchName # "--no-ff" creates a commit that there was a branch merge
#                                   so in the future when you are looking at your commit log
#                                   you know when exactly when you merged one branch into another
$ git push origin oldBranchName
$ git branch -D newBranchName # deletes local branch newBranchName
$ git push origin --delete newBranchName # deletes remote branch newBranchName
```
