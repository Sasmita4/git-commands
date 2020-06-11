Configuring Git
          1.1 Setting up the Identity

        git config --global user.name "<gitusername>"
          Ex : git config --global user.name "shekark"
        git config --global user.email "<emailaddress>"
          Ex : git config --global user.email "shekar.kusukuntla@alacriti.com"
          1.2 To Unset the config value

        git config --global --unset user.email
          1.3 Setting up Meld tool

        git config --global merge.tool meld
          1.4 To set the colors

        git config --global color.ui true
          1.5 To Check Your Settings

If you want to check your settings, you can use the git config --list command to list all the settings Git can find at that point:
          git config --list
          1.6 To Getting Help

If you ever need help while using Git, there are three ways to get the manual page (manpage) help for any of the Git commands
          git help <verb>
          git <verb> --help
          man git-<verb>
               For example, you can get the manpage help for the config command by running

          git help config
 

2. Cloning and Creating Projects
      2.1 Clone Repository

      git clone http://username@repostitoryHostName/reponame
        Ex : git clone http://shekark@192.168.75.216/orbipay.git
3. Staging and Committing Changes
      3.1 To know the status of the working directory

 

The below command show status like untracked files(new files added) , and modified files, and number of commits need to push.This is the most important and most used command.
       git status
       3.2 To Add files to Staging area

       git add <filename1> <filename2>
              The git add command does two operations.
                 1. Add the Untracked files to the staging area.
                 2. Add the modified Tracked file to the staging area.

       3.3 To Rename the File in work-space and in the index

       git mv <filename>
       3.4 To Remove file and stage
       git rm <filename1> <filename2>
        3.5 To Commit

       git commit -m 'refs #Jira-TicektNumber commit description'
       git commit -a is equivalent to running git add on all filenames that existed in the latest commit or tracked files, and then running git commit.
4. Working with Remote Repositories  OR Sharing and Updating Projects
     4.1 Push your changes to Central Repository

      git push origin <branchname>
      Ex: git push origin master

      4.2 To get updates from Central Repository

      git fetch
            This will get the updates from central repository and update the remote tracking branches.

       4.3 To apply the remote changes onto your branch

       git rebase -p origin/<branchname>
              This will update the local working directory and apply your changes on top of it. 

          Ex :  git rebase -p origin/master

       4.4 To push your local "feature_OPAY-999" branch to the "feature_OPAY-999" branch on the remote project

       git push origin feature_OPAY-999:feature_OPAY-999
       4.5 Deleting Remote Branches

       git push [remotename] :[LocalBranchName]
              Syntax Explanation :

         git push [remotename] [localbranch]:[remotebranch]
                  Take nothing on my side and make it be [remotebranch].

            Ex : git push origin :feature_OPAY-999
        4.6 Git Pull with Rebase

               If you want git to do a rebase instead of a merge when pulling you can run git pull like this:

               git pull --rebase
                    Instead of typing the above (or making an alias for it), you can tell git to automatically rebase when pulling.
               git config --global pull.rebase true
 Do not use 'git pull' -- Ex: git pull origin <branchname> to pull remote branch changes to local branch Always use (while on the current branch) :
               git fetch origin  
               git rebase −p origin/<branchname>
               Purpose:
                 1. 'git pull' creates an unwanted merge, which makes it hard to track history.
                 2. Also makes reverting a commit complicated.
