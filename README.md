# Data for gen711 and 811 lab exercises

## Lab 1 (take home lab, 01/26/24)
- **Step 1.** Sign up for a github account here 
- **Step 2.** From a from your github account, fork this repository: https://github.com/jthmiller/gen711-811.git
- Shortcut to the 'fork' [button](https://github.com/jthmiller/gen711-811/fork) I am not sure if this works  
- **Step 3.** Install visual studio code from [here](https://code.visualstudio.com/Download) 

## Lab 2 (02/02/24)
- **Step 1.** Ensure that vscode is installed on your machine (either lab computer OR laptop).
- **Step 2.** Set up remote-ssh so that you are logged in to RON when you open vscode [see here](https://code.visualstudio.com/docs/remote/ssh). 

First, open 'terminal' on your mac. Then, after generating the keys, you will restrict the permissions on the private key file. For macOS / Linux, run the following shell command, replacing the path to your private key if necessary:
```
cd ~/.ssh
ssh-keygen -t ed25519 -b 4096
chmod 400 ~/.ssh/id_ed25519
```
**For Windows**, run the following command in PowerShell to grant explicit read access to your username:
```
icacls "privateKeyPath" /grant :R
```
Then navigate to the private key file in Windows Explorer, right-click and select Properties. Select the Security tab > Advanced > Disable inheritance > Remove all inherited permissions from this object.

- **Step 3.** If you set up remote ssh correctly, you can clone your gen711-811 fork in your home directory on the RON server. This will create 'gen711-811' repo in your home directory. Changes made here can be pushed to github. Replace <YOURGITHUBUSERNAME> with the github username you created.
```
cd $HOME
git clone https://github.com/<YOURGITHUBUSERNAME>/gen711-811.git
```

- **Step 4.** Now that you are connected to RON, make a lab notebook in your repo to be graded each week. In vscode terminal, go to 'file' --> 'new text file'. Save this empty file as 'yourlastname_yourfirstname.md'. Keep notes in this file as demonstrated by your instructor to get full attendence points.

- **Step 5.** Save a change to your lab notbook, and use vscode's built-in github menu to push the changes to your  version at github. Confirm that your notebook has been added to your github repo. 

- **Step 6.** Follow along with the instructor for an introduction to command line. Save your notes periodically and push the saved changes multiple times throughout lab.   


- **Step 7.** Save your vscode workspace in your repo on RON. Go to 'File' --> 'Save Workspace As' and save it to the 'gen711-811' folder on RON. This way, you can load this workspace each week to pick up where you left off. 

To get new course files added to your repository later, you will need to add the original repository (the one you forked) as a 'remote' [see here for help](https://stackoverflow.com/questions/3903817/pull-new-updates-from-original-github-repository-into-forked-github-repository),[and here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)  
To add updates from the gen711-811 repo:
```
cd gen711-811
git remote add upstream https://github.com/jthmiller/gen711-811.git
git fetch upstream
git merge upstream/master master
```
Note, git merge is like "git pull" which is fetch + merge. Or, better, you can replay your local work on top of the fetched branch like a "git pull --rebase"
```
git rebase upstream/master
```