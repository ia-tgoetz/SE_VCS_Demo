# SE Demo Script

## Part 1 - Create local repo and connect to remote repo

### Create local Git Repo on you dev machine

Open the local folder you want your repo to exist in.
For this demo it will be the directory that you are going to deploy the Docker stack in and persist files.
For anyone not using containerization, it may just be the data directory of an Ignition install.

Create a file in that directory called .gitignore.
the .gitignore file will tell git what files in the directory to "ignore" and not version control.
For this demo, use the following 

Open a terminal at that directory.
Run the following command to create a git repo there:
''''
git init .
''''

Create a remote remote repo in GitHub

Then run add the remote repo:
''''
git remote add origin {Repo URL}
''''

### Add to staging and commit to remote repo

Next add the locally tracked files and commit them to the local repo with the following commands:
''''
git add .
git commit -m "initial commit"
''''

## Part 2 - Edit a resource and push changes

### Edit resource

Create a resource by:
- Start Ignition gateway (if not started already)
- Open designer
- Create a Perspective view and add a label with whatever text you want in it

In the command line run the following command to view changes:
''''
git status
''''
*Note: If using VScode, this is a good time to jump back into that window and show the diffs for the actual files in the source control extension

### Commit resources and push to remote repo

In the command line run the following commands to commit those resources and push to the remote repo:
''''
git add .
git commit -m "Added Perspective view"
git push -u origin master
''''

