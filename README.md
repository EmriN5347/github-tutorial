# GitHub Tutorial

*_by Emri Nesimi_*

---
## Git vs. GitHub
* Git is an open-source tool developers install locally to manage source code 
* GitHub is an online service (cloud base) which coders or developers could use git to connect and upload with each other for collaberation purposes.


---
## Initial Setup
1. Setup a GitHub account: 
![](images.jpg)
    a. Go to the sign up and create the account with an email and password
2. When your in yor command line type ``git config --global user.email "you@example.com"``  
    a. Don't copy/paste it because you need to use your email  
    b. Don't forget the quotes
3. Then type ``git config --global user.name "Your Name"``` 

#### Generating and connecting an SSH key
* go to your root directory ``(cd~)``
* type this into your ide ``ssh-keygen -t rsa -b 4096 -C "you@example.com"``  
    * make sure to use your email in the quotations
    * Then click enter slowly until you see this image
```
The key's randomart image is:  
+--[ RSA 4096]----+
|       .o o..    |
|       o +Eo     |
|        + .      |
|         . + o   |
|        S o = * o|
|           . o @.|
|            . = o|
|           . o   |
|            o.   |
+-----------------+
```

* `eval "$(ssh-agent -s)"` starts the agent in the background
* `ls -al ~/.ssh` you should now see a file named `id_rsa.pub`
* `cat ~/.ssh/id_rsa.pub` then copy _all_ of the result to your clipboard (it should start with `ssh-rsa` and at the end should have your email adress)
* Go to [https://github.com/settings/keys](https://github.com/settings/keys)  
    * Click new SSH Key
    * Create a Title: ide50
    * Key: paste your ssh key
    * Click the green button that says Create SSH key
* Back into your ide type ``sudo nano ~/.ssh/config``
* Then paste 
 ```
 Host github.com
 Hostname ssh.github.com
 Port 443
 ```
* `control+X` to exit, then press Y` then `ENTER`
* `ssh -T git@github.com`
* Type yes, press `ENTER`, and you should see
> Hi "username"! You've successfully authenticated, but GitHub does not provide shell access.


## Repository Setup
1. When you create a repo you need to do `git init` 
2. Create a README.md file into your repo
3. Then you need to create a repo in github.
    a. sign into github
    b. On the left side there is the reopisitory section, then you click the big green button that says new.
    c. when you create the repo you need it to have the same name as you have in you cs50 ide.
    d. Then it will direct you to the quick setup page, and you have to click the ssh button.
    e. Look for the section that says **or push an existing repository from the command line**  
    f. Copy the `git remote add origin git@github.com:"your accout"/"your repo name"` into your command line.
4. In the README.md add what you need to add, then `c9` into README.md 
5. when your done working in the README file then in you command line add it to the stage and commit it with a message what you have done in the file.
6. Then you have to do `git push` so it could update in github.

   



---
## Workflow & Commands
* `git init` - Initializes git in our directory (now we call it repository) for version control: only do this in the beginning to be for effiecent.
    * To do it in the directory you want to turn into repository
   *  **Never do it in the root diectory!!**
   *  If you init in the wrong directory you have to unitilize git be doing `rm -rf .git`

* `Git status` (Not mandatory but very useful)
    * Used to see if a file has changed
    * To see if you forgot to add the file to the stage
* `git add` - adds any changes made in file to the stage to be committed.  
* This command could be used in many ways. You could choose what you want to add to the stage. Ex: If you want to add all `git add .` or add only one thing `git add filename`
* `git commit` - take a "snapshot" of the files on the stage that you added. Then you need to right a message in present tense ** dont do it in past tense ** 
* `git push` - This allows you to import your commits to github and allows others to view your updated work on a project. This sends to remote 
* `git remote` - This shows were your commit will go after you push them. This allows the user to know if they are sending the work to the right location.
* `git log` - This shows the history of your past commits
* `git revert` - This is used to redo a commit you have done in the pass with the use of git log.






---
## Rolling Back Changes

* `git checkout -- filename` - Suppose you're working on a repo with someone else, and you accidentally started editing a file that you shouldn't have (because you know you're going to get a merge conflict, and you'd rather avoid it altogether than have to deal with it).
* `git reset head` - You would want to remove the broken file from the stage with this command.
* `git log`&`git revert` - you get the "SHA" key then you type `git revert` then paste the "SHA" key to remove a paste commit.




---
## Fork/Clone

* "Forking" a project is when you copy another repository. Forking is creating a bridge from the original to your repo, and you could create pull request to improve the orignal user's project
1. "Cloning" is a way to copy the things in that repo into your ide. 
    a. go to the clipboard and copy the ssh key.
    b. then go to your ide
    c. type `git clone` then paste the ssh key
    d. finally cd into that file and have fun











