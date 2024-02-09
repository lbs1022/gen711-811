## Lab 2 (02/02/24)

For this lab, we will:
- On windows, use putty to connect to RON to change your password 
- Install the 'remote-SSH' extension in visual studio code (vscode) (only do if you did not do this)
- Use vscode to connect (ssh) to the UNH teaching HPC (RON)
- Clone the gen711-811 github in your home directory on RON

### Windows (open putty and connect with ssh)
Username example: jtm1171@ron.sr.unh.edu   
Password example: jtm1171zfG!1    

### Set up remote-ssh so that you can connect to RON through vscode [see here](https://code.visualstudio.com/docs/remote/ssh). 
1. Open up vscode and click the 'building blocks' icon on the left hand side of vscode 
2. In the upper left search bar, type 'Remote SSH'
3. Click 'install' 
4. Open the vscode 'command pallete' by pressing 'CMD + Shift + P'. A little bar at the top of the screen should pop up. Begin to type 'Remote-SSH: Add New SSH Host...'. Before you get too far, you should see it pop-up. Click it. If you are asked what the host operating system is, click **LINUX**
5. **Enter your username and password when prompted.** The username is the students id.
   
Username example: jtm1171@ron.sr.unh.edu  

Password example: jtm1171zfG!1  

The password is your username + zfG!1 
Example: Your initial password for the class server (Ron) is: ```acb1078zfG!1``` The server name is ron.sr.unh.edu and your username is ``` acb1078 ```  
7. Click the config file that contains .ssh folder
8. A window in the lower left should pop-up. **Click connect.** A new window should pop up 
9. You are logged in to RON when a new vscode pops up. 

### GITHUB Clone gen711-811 
If you set up remote ssh correctly, you are now in your home directory at RON. You can clone your gen711-811 fork in your home directory. This will create 'gen711-811' repo in your home directory. Changes made here can be pushed to github. 

To run this command, you MUST replace <YOURGITHUBUSERNAME> with your **github username** that you created before class.
```
cd $HOME
git clone https://github.com/<YOURGITHUBUSERNAME>/gen711-811.git
```
### Make a lab notebook  
Now that you are connected to RON, make a lab notebook in your repo to be graded each week. In vscode terminal, go to 'file' --> 'new text file'. Save this empty file as 'yourlastname_yourfirstname.md'. Keep notes in this file as demonstrated by your instructor to get full attendence points.

### BONUS if everything goes well up until this point

**Save your vscode workspace in your repo on RON and your local machine.**  
Go to 'File' --> 'Save Workspace As' and save it to the 'gen711-811' folder on RON. This way, you can load this workspace each week to pick up where you left off. 

**Generate ssh-keys to log into RON without usernames and passwords**  

First, open 'terminal' on your mac. We are going to use the terminal to generate the keys and restrict the permissions on the private key file. For macOS / Linux, run the following shell command, replacing the path to your private key if necessary:
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
If that doesn't work, we can try:
```
cat ~/.ssh/id_rsa.pub | ssh user@12.34.56.78 "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys
```
</details> <!-- end for mac-->
<br>
 <details><summary>For Windows</summary> 

**For Windows**, run the following command in PowerShell to grant explicit read access to your username:
```
icacls "privateKeyPath" /grant :R
```
Then navigate to the private key file in Windows Explorer, right-click and select Properties. Select the Security tab → Advanced → Disable inheritance → Remove all inherited permissions from this object.

<br>

### Next Week

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
