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
For Windows, run the following command in PowerShell to grant explicit read access to your username:

```
icacls "privateKeyPath" /grant :R
```
Then navigate to the private key file in Windows Explorer, right-click and select Properties. Select the Security tab > Advanced > Disable inheritance > Remove all inherited permissions from this object.


- **Step 3.** If you did step 4, you can clone your gen711-811 fork in your home directory on RON with:  
```
git clone https://github.com/YOURUSERNAME/gen711-811.git
```
To get new course files added to your repository later, you will need to add the original repository (the one you forked) as a 'remote' [see here for help](https://stackoverflow.com/questions/3903817/pull-new-updates-from-original-github-repository-into-forked-github-repository)  
[and here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)  
To add updates from the gen711-811 repo:
```
cd gen711-811
git remote add upstream https://github.com/jthmiller/gen711-811.git
git fetch upstream
git merge upstream/master master
```
## note, git merge is like "git pull" which is fetch + merge. Or, better, you can replay your local work on top of the fetched branch like a "git pull --rebase"
```
git rebase upstream/master
```