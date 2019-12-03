# GitHub Tutorial

_by Melih Yumusak_

---
## Git vs. GitHub
 Git|Github 
 -------------------|-------------------
 Version controle system.| Has certain user interface options. ___**EX:** The ablity edit whitout comand prompt.___ 
 Comand line tool.| Used for colobration 
 Desktop interface. | Website
 Localy saved. | Saved on cloud 
**GIt** is a program used to track changes during software development.

**GitHub** is a repository holding system that allows the user to share and collaborate software on a cloud based system. 


---
## Initial Setup

#### Making a github 
 1. Go to github.com 
 2. Click the the green button that _says singn up for github_
 3. Fill in the nesesary info ie a _username, email and, password_ _(Hstat student your school email whitout everything after the @)_
 4. Select a plan _(HSTAT students pick free)_ 
 5. Skip the Welcome to github page if you would like
 6. Verify the email

#### Setting up **User Info**
 1. In the command line type `git config --global user.email "you@example.com"`
    - Replace `"you@example.com"` whit your own email. 
    - The quotes are necessary. 
 2. Type `git config` `--global user.name "Your Name"`

#### Setting up SSH 
 1. Go to root directory ` cd ~ `
 2. `ssh-keygen -t rsa -b 4096 -C "your@email.com"`
    - Press enter until you see key's randomart
 3. Type `eval "$(ssh-agent -s)"`
    - Will start agent
 4. Type `ls -al ~/.ssh` 
    - You will see a file named `id_rsa.pub`
 5. Type `cat ~/.ssh/id_rsa.pub` 
 6. Copy all results _will start whit_ `ssh-rsa`
 7. Click on the link [Github SSH](https://github.com/settings/keys)
    - New SSH key 
    - Title- ide50 
    - Paste SSH key 
    - Click on the <span style="color:Green">green</span> **_Add SSH key button_**
  8. Go to your ide type `sudo nano ~/.ssh/config`
  9. Paste   `Host github.com
      Hostname ssh.github.com
      Port 443`  
  10. **control+X** to exit, then press **Y** then **ENTER** 
  11. Type `ssh -T git@github.com`
  12. Type _**Yes**_ & _**Enter**_

#### IDE 50 setup _(Optional but useful)_
  1. Go to top-left corner of the IDE press CS50 IDE then **Preferences**
  2. Left side of the new window click **User settings** 
  3. On the right click **Enable Preview to ON**

#### Auto save 
  1. On the *LEFT* side  scroll down click **Experimental**
  2. Change **Auto-Save** dropdown to On **Focus Change**

#### SSH importance 
 This is used in order to help solve conectivity problems in a cloud. SSH (Secure Shell or Secure Socket Shell) network protocol that gives user particular system administrator. Secure way to access a computer over unsecured network

---

## Repository Setup
**Do not init git in tilda (Main)**
 1. Make a repo in your ide `Mkdir Name` _(Hstat students call it github learning)_
 2. Type `cd Name`
 3. Type `git init`
 4. Type `touch` README.txt
 2. Type `git add .` This will stage the changes you just made 
 3. Type `git commit -m "phrase"` This will ensure that any changes you have made will be saved on the cloud 

#### New repo on git 
 1. Go to github.com 
 2. Click on the plus sign in the top right 
 3. Click on _New Repository_
 4. The repo name should be the same as the repo made on github or you will get a push error 
 5. Click Create repository
 6. Make sure SSH is picked
 7. Copy and paste **…or push an existing repository from the command line**
   - EX 
   
         `git remote add origin git@github.com:MelihY9151/Testtest.git`
  
         `git push -u origin master`

 The remote bond between our repository and a outside one.The add is we are adding a remote to uour ide repo. Origin is the name of the repo it is a common name. Finally the url is the place the repo will head if you push.  

 Git push will send your repo to github where it will be a new copy of it.  

---


## Workflow & Commands
  Git status-This is used to determine whethier git is initilized and to determine if there are any unsaved changes to git. 
  
  Git add-This will alow you to stage any changes that have been added to the repo. 
  
  Git commit-This will snapshot any added things to your cloud or harddrive. 
  
  Git push-This will send a copy of the repo to cloud or to github. 


---
## Rolling Back Changes

Undo edit- `git reset HEAD _Name_` This will delet any unsaved edits that were done since last commit. 

Undo add- `Run git reset _Name_ ` This will unstage all files that have been staged. 

Undo commit- `git reset HEAD` This will revert the most recent commit.  

Undo push- `git push origin --delete _Name_` This will delet the push. 