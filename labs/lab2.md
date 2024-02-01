# Lab 2 (02/02/24)

## Step 1.

- Ensure that VSCode is installed on your machine (either lab computer OR laptop).

## Step 2. 

- Set up remote-ssh so that you are logged in to RON when you open VSCode [see here](https://code.visualstudio.com/docs/remote/ssh). 

 <details><summary>For Mac</summary> 

**For macOS / Linux**, run the following shell command, replacing the path to your private key if necessary:

- First, open 'terminal' on your Mac. We are going to use the terminal to generate the keys and restrict the permissions on the private key file. 
```
cd ~/.ssh
ssh-keygen -t ed25519 -b 4096
chmod 400 ~/.ssh/id_ed25519
```
<br>

- Next, share the public key with the Ron server
```
ssh-copy-id username@ron.sr.unh.edu
```
</details> <!-- end for mac-->
<br>
 <details><summary>For Windows</summary> 

**For Windows**, run the following command in PowerShell to grant explicit read access to your username:
```
icacls "privateKeyPath" /grant :R
```
Then navigate to the private key file in Windows Explorer, right-click and select Properties. Select the Security tab → Advanced → Disable inheritance → Remove all inherited permissions from this object.

</details> <!-- end for windows-->

## Step 3.

- If you set up remote ssh correctly, you can clone your gen711-811 fork in your home directory on the RON server. 

```
git clone https://github.com/<username>/<repo>
```
- This will create 'gen711-811' repo in your home directory. Changes made here can be pushed to GitHub. Replace \<username> with your GitHub username, and \<repo> with your forked repo (probably "gen711-811")


## Step 4.

- Now that you are connected to RON, make a lab notebook in your repo to be graded each week. In VS Code terminal, go to 'file' → 'new text file'. Save this empty file as 'lastname_firstname.md'. (replacing with your last/firstname). 

<center><b>Important<br>Keep detailed notes, these will be graded for attendance!!</b></center>

## Step 5.

- Save a change to your lab notbook, and use vscode's built-in github menu to push the changes to your version at github. Confirm that your notebook has been added to your github repo. 

## Step 6.
- Follow along with the instructor for an introduction to command line. Save your notes periodically and push the saved changes multiple times throughout lab.

    - you can use the `source control` tab in VS Code
    - or through the terminal 

```
git add lastname_firstname.md
git commit -m "update notes"
git push
```
- through terminal may cause some issues, we can go over in lab how to sign in on Ron

## Step 7
- Save your VS Code workspace in your repo on RON. Go to 'File' → 'Save Workspace As' and save it to the 'gen711-811' folder on RON. This way, you can load this workspace each week to pick up where you left off. 

- To get new course files added to your repository later, you will need to add the original repository (the one you forked) as a 'remote' 

    - [help](https://stackoverflow.com/questions/3903817/pull-new-updates-from-original-github-repository-into-forked-github-repository)
    -  [and more help](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)  

<!-- https://www.cs.unh.edu/~cs925/assignments/gitlab.html -->

- To add updates from the gen711-811 repo:

```
cd gen711-811
git remote add upstream https://github.com/jthmiller/gen711-811.git
git fetch upstream
git merge upstream/master master
```

- Note, git merge is like "git pull" which is fetch + merge. Or, better, you can replay your local work on top of the fetched branch like a "git pull --rebase"

```
git rebase upstream/master
```
