# Github Push


Open Terminal.

• Change the current working directory to your local repository that you want to push.

`
git add .
`

`
git commit -m "Add existing file"
`

`
git push origin master
`

## Troubleshoot:
 
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/user/repo.git'
hint: Updates were rejected because the tip of your current branch is behind
 
 
`
git rebase origin/master
`

https://help.github.com/en/articles/adding-an-existing-project-to-github-using-the-command-line
