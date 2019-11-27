# GitHub Tutorial

*_by Emri Nesimi_*

---
## Git vs. GitHub
* Git is an open-source tool developers install locally to manage source code 
* GitHub is an online service (cloud base) which coders or developers could use git to connect and upload with each other for collaberation purposes.


---
## Initial Setup
1. Setup a GitHub account:     
    a. Go to the sign up and create the account with an email and password
2. When your in yor command line type ``git config --global user.email "you@example.com``  
    a. Don't copy/paste it because you need to use your email  
    b. Don't forget the quotes
3. Then type ``git config --global user.name "Your Name"``` 

#### Generating and connecting an SSH key
* go to your root directory ``(cd~)``
* type this into your ide ``ssh-keygen -t rsa -b 4096 -C "you@example.com"``  
    * make sure to use your email in the quotations
    * Then click enter slowly until you see this image
```
    * The key's randomart image is:  
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

   



---
## Workflow & Commands
* `git init` - Initializes git in our directory (now we call it repository) for version control: only do this in the beginning to be for effiecent.
    * To do it in the directory you want to turn into repository
   *  **Never do it in the root diectory!!**

* Git status (Not mandatory but very useful)
    * Used to see if a file has changed
    * To see if you forgot to add the file to the stage




---
## Rolling Back Changes