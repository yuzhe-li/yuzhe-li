
# How to connect atom to github

## 1. Setup ssh public/private key to github (Done)


https://support.atlassian.com/bitbucket-cloud/docs/set-up-an-ssh-key/



1. generate public/private key on each pc
https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
2. add public ssh key to my github account
https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

## 2. Set up two-factor authentication for github (Done)
already activated two-factor authentication
- using google authenticator on my iphone for my account
https://docs.github.com/en/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication


## 3. need to create a personal access token,  after setting up two-factor authentication (Done)
already generated, see note
https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token

if shows some error, need to delete and keychain access, and re-enter the username, and use the personal token as password

https://docs.github.com/en/get-started/getting-started-with-git

## 4. need to use http instead of ssh  after two-factor authentication
Switching remote URLs from SSH to HTTPS
- git remote -v
- git remote set-url origin https://github.com/USERNAME/REPOSITORY.git

https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories#switching-remote-urls-from-ssh-to-https

## 5. How to add an exsting local folder to github repo
`git init -b main
git add .
git commit -m "First commit"
git remote add origin  <REMOTE_URL>
git push -u origin main`
https://docs.github.com/en/github/importing-your-projects-to-github/importing-source-code-to-github/adding-an-existing-project-to-github-using-the-command-line

## 6. how to use atom-git
https://flight-manual.atom.io/using-atom/sections/github-package/
## 7. How to clone exising github repo to local
`git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY`
https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository-from-github/cloning-a-repository
#
## 8. How to delete .DS_Store file and prevent to upload to github 
https://stackoverflow.com/questions/107701/how-can-i-remove-ds-store-files-from-a-git-repository

1. delete .DS_Store file locally 
`find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch`

2. add .DS_Store file to .gitignore list (create .gitignore file if not exist)
` echo .DS_Store >> .gitignore

git add .gitignore`

3. commit and push to github

`git commit -m '.DS_Store banished!'

git push origin main
`

## 9. Commend line push and fetch 
fetch: 
`git fetch`

push:
`git push -u origin main`


