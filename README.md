## Data needed for gen711 and 811

- Sign up for a github account

- From a web-browser, fork this repository: https://github.com/jthmiller/gen711-811.git to your own github account
    - To get new updates, you will need to add the original repository (the one you forked) as a remote 
        - https://stackoverflow.com/questions/3903817/pull-new-updates-from-original-github-repository-into-forked-github-repository 

- Set up remote-ssh so that you are logged in to RON when you open vscode
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
# or, better, replay your local work on top of the fetched branch
# like a "git pull --rebase"
```
git rebase upstream/master
```