### Clone repository (do once)

```
git clone git@github.com:zenaiev/toponium
cd toponium
```

If the first command does not work, you need to create a github account and generate an SSH key:

 - register a new account at [github.com](https://github.com/)
 - generate and add a new ssh key (enter your correct email address):
   ```
   ssh-keygen -t rsa -b 4096 -C "your.email@email.com"
   ssh-add ~/.ssh/id_rsa
   ```
 - add this key to your github account:
   ```
   cat ~/.ssh/id_rsa.pub
   ```
   Copy the output, go to [github.com](https://github.com/), login into your account, go to settings (click on the round icon on top right), go to "SSH and GPG keys", press "New SSH key", enter the output copied above (it should start with `ssh-rsa` and end with your email) into the field "Key" and press "Add SSH key"
 - verify that everything is correct:
   ```
   ssh -T git@github.com
   ```
   You should see something like: `Hi zenaiev! You've successfully authenticated, but GitHub does not provide shell access.`
 - now proceed with cloning the repository

If you need the repository to read the files only, it is possible to clone it without the SSH key:
```
git clone https://github.com/zenaiev/toponium
```
but then you will not be able to push new files or any your updates to it.

### Update your local repository (to pull external updates)

```
git pull
```
If this command produces an error ending with `fatal: Need to specify how to reconcile divergent branches.`, run:
```
git config pull.rebase false
```
and repeat.

### Add your new or updated files

```
git add matrix/matrix1.txt matrix/matrix2.txt
git commit -m 'describe your commit'
git push
```
If the last command produces an error like ` ! [rejected]        main -> main (fetch first)`, you need to pull the external changes first:
```
git pull
```
