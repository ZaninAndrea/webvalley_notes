# Git
[Presentation](https://docs.google.com/presentation/d/1vqltkpxChZsr7Vst3RLIEnFew3vBJwQCGk01a1lhH3g/edit?usp=sharing)
## New commands
* `git rm --cached` 
* `git push --tags` push tags on the remote
* `git status`

## Configuring git
* `git config --global user.name <name>`
* `git config --global user.email <email>`

## Github
You can connect to github through ssh. Steps to configure:
* create an ssh key `ssh-keygen -t rsa -C <email>`, you can use an empty passphrase so that you will not need to re-enter it every commit
* `ssh -T git@github.com` to test
* add origin ssh `git remote add origin git@github.com:<username>/<repoName>.git`