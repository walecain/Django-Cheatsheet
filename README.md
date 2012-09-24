=================
Django-Cheatsheet
=================

This is a cheatsheet created by @bobbyong and @johnking7 to improve our productivity while working on a Django freelance project. Feel free to use or improve this document wherever you see fit. :)


======
Django
======

Start Project:  
django-admin.py startproject <projectname>

Run Server:  
python manage.py runserver

Start App:  
python manage.py startapp <appname>

Sync Database (Create tables for first time use):  
python manage.py syncdb

Declare Required Python Modules:  
pip freeze > requirements.txt


===
Git
===

To list git commands:
git --help

To get specific help on a command (e.g. checkout)
git checkout --help

Check Git Remote:  
git remote  
git remote -v (to check URL of git remote alias)

Add New Remote:  
git remote add <git name. Example: origin> <git URL ending with .git>

Remove Git Remote:  
git remote rm <git name. Example: origin>

Credential Caching Tool on Windows (save typing username & password)
---
https://github.com/blog/1104-credential-caching-for-wrist-friendly-git-usage
---

gitk - graphical repository viewer. From there you can open git-gui (for some reason git-gui as a standalone command isn't working for me)

-----
Branching

To create new branch locally
git checkout -b <new branch name>
To switch branches
git checkout <branch name e.g. master>
To view local branches
git branch
To view local and remote branches
git branch -a
To push to a new branch called "newFeature" (assuming your remote is named origin)
git push origin newFeature
Additionally that will create the remote branch if it doesn't already exist

Generally commit files to the branch you're working on before switching otherwise it gets confusing. For example if you add a new file (newfile.txt) to a branch called "newFeature", 
then checkout your master branch, you will see newfile.txt as an unstaged commit. Which, if there's a lot going on, could mean that it gets committed to master not 
the other branch called "newFeature". However if you're on branch "newFeature", commit the changes, then switch to master and run "ls" you won't see newfile.txt (yay), meaning you can't accidentally commit it to the master branch.
-----

To show commit history:
git log & git reflog (try both to see differences)

To move back 1 commit:
git reset --hard HEAD@{1}


Or to move back to a previous commit type reflog - check the hash next to the commit you want then type
git reset --hard <appropriate hash>

======
Heroku
======

Login to Heroku:  
heroku login

Run One-off Heroku Commands:  
heroku run <subsequent commands. Example: python manage.py syncdb>

Check State of Dynos:   
heroku ps

Review Logs:  
heroku logs

Open App on Browser:  
heroku open


=====
South
=====

After Installing South:  
python manage.py syncdb

Initial South Migration (New App):  
python manage.py schemamigration <appname> --initial  
python manage.py migrate <appname>

Subsequently App Migrations:  
python manage.py schemamigration <appname> --auto  
python manage.py migrate <appname>



Converting an Existing App to South:  
python manage.py convert_to_south <appname>

Subsequently App Migrations:  
python manage.py schemamigration <appname> --auto  
python manage.py migrate <appname>


==============
Django-Userena
==============

Step-by-Step Tutorial:  
http://bobbyong.com/blog/step-by-step-guide-on-configuring-django-userena/


==========
PostgreSQL
==========

Step-by-Step Tutorial:  
http://bobbyong.com/blog/installing-postgresql-on-windoes/