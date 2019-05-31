# GIT - Basic Commands    [Incomplete....]

| Git Commands                   | Git Task                         | Notes                                                        |
| ------------------------------ | -------------------------------- | ------------------------------------------------------------ |
| git status                     | Status                           | List the files have been changed and need to add or commit later |
| git log                        | Commit History                   | Commit ID is the leading characters of the change set ID, up to 10 and it is unique |
| git add filename               | Add file                         | Add one file to staging                                      |
| git add *                      | Add files                        | Add all files to staging                                     |
| git commit filename            | Commit file                      | Commit one file                                              |
| git commit  *                  | Commit files                     | Commit all files                                             |
| git push origin master         | PUSH                             | Send the changes to the master branch of remote repository   |
| git pull origin master         | PULL                             | update the local repository from remote repository           |
| git fetch                      |                                  |                                                              |
| git init                       | Create a repository              | Create a new local repository                                |
| git commit -m "commit message" | Commit changes to head           | Commit changes to head before sending to the remote repository |
| git reset --hard origin/master |                                  |                                                              |
| git reset --soft origin/master |                                  |                                                              |
| git reset --hard HEAD~         | Reset changes since last commit  | Reset every changes after last commit, and delete every changes after last commit and files add or change can not find in the git status |
| git reset --soft HEAD~         | Reset changes since last commit  | Reset every changes after last commit but reserve every changes and can be modified and commit again |
| git commit -ammend             | Commit                           | Commit without create a new commit, usually for slightly change and keep in the latest commit |
| git --version                  | Version                          | Check the Git Version                                        |
| git branch                     | Check branch                     | Check every branch in the repository                         |
| git branch *branchname         | Create a new and branch          | Crate a new branch and name it                               |
| git checkout *branchname       | Switch branch                    | Switch to a particular branch in the repository              |
| git diff                       | Check the difference in branches | Check the differences between master branch and current branch |
| git merge                      | Merge branch                     | Can use to merge the branch into master branch               |
| rm .git -rf                    | Delete Local Repository          | Delete the git file in the current Repository, right click the repository file and execute the GIT BASE first |



Other Useful Commands:

| Commands          | Task                           | Note |
| ----------------- | ------------------------------ | ---- |
| :wq               | Exit Vim mode                  |      |
| ls                | open the current folder        |      |
| touch             | create a file                  |      |
| clear             | clear the screen               |      |
| **vim** test.txt  | edit the test.text file in Vim |      |
| **more** test.txt | open the file test.txt         |      |

