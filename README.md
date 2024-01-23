## Data needed for gen711 and 811

- Sign up for a github account
- Fork this repository: https://github.com/jthmiller/gen711-811.git
    - This will give your own copy of the repo in your github account
    - You have to add the original repository (the one you forked) as a remote to get new updates.
        - https://stackoverflow.com/questions/3903817/pull-new-updates-from-original-github-repository-into-forked-github-repository 


### To add updates from the gen711-811 repo
cd gen711-811
git remote add upstream https://github.com/jthmiller/gen711-811.git
git fetch upstream

### then: (like "git pull" which is fetch + merge)
git merge upstream/master master

# or, better, replay your local work on top of the fetched branch
# like a "git pull --rebase"
git rebase upstream/master