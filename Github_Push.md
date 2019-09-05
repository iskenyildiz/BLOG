# Github Push


Open Terminal.
    • Change the current working directory to your local repository.

`
git add .
`
`
git commit -m "Add existing file"
`
`
git push origin master
`

Troubleshoot:
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/iskenyildiz/DHT11_portable.git'
hint: Updates were rejected because the tip of your current branch is behind

`
git rebase origin/master
`
