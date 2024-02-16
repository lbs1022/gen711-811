# Lab3 - 2/16/24

## Pre-lab

1. Open up vscode
2. Control + shift + 'p' to open command prompt (command + shift + p on apple)
3. Start typing 'Connect to...' and the 'Connect to host' menu item will pop up. Select it
4. If asked, connect to ron.sr.edu host
5. Enter your RON username if prompted
6. Enter your RON password when prompted
7. You should see an 'open folder' on the left. Click it. The command prompt will have something like ```/home/unhAW/jtmiller/```. Click 'ok' open your home directory. If you saved a lab notebook to RON, you should see it on the left in a list of files. Click on it to open it. 
8. Next, we need to clone your gen711-811 github repo that you forked. Skip this step if you have done this already 
```
cd $HOME
git clone https://github.com/<YOURGITHUBUSERNAME>/gen711-811.git
```
9. Finally, we need to pull the latest updates to this repo. Run these commands:
```
cd gen711-811
git remote add upstream https://github.com/jthmiller/gen711-811.git
git fetch upstream
git merge upstream/master master
cd ~
```

## Lab