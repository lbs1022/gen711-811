# Data for gen711 and 811 lab exercises

Step 1. Sign up for a github account  
Step 2. From a from your github account, fork this repository: https://github.com/jthmiller/gen711-811.git  
Step 3. To get new course files added later, you will need to add the original repository (the one you forked) as a remote of your repository [see here](https://stackoverflow.com/questions/3903817/pull-new-updates-from-original-github-repository-into-forked-github-repository)  
Step 4. Set up remote-ssh so that you are logged in to RON when you open vscode [see here](https://code.visualstudio.com/docs/remote/ssh)  

- In your home directory, you will clone your gen711-811 fork
```
git clone https://github.com/YOURUSERNAME/gen711-811.git
```

### To add updates from the gen711-811 repo
```
cd gen711-811
git remote add upstream https://github.com/jthmiller/gen711-811.git
git fetch upstream
```
### then: (like "git pull" which is fetch + merge)
```
git merge upstream/master master
```
### or, better, replay your local work on top of the fetched branch like a "git pull --rebase"
```
git rebase upstream/master
```