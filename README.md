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
```
git init .
```

Create a remote remote repo in GitHub

Then run add the remote repo:
```
git remote add origin <Repo URL>
```

### Add to staging and commit to remote repo

Next add the locally tracked files and commit them to the local repo with the following commands:
```
git add .
git commit -m "initial commit"
```

## Part 2 - Edit a resource and push changes

### Edit resource

Create a resource by:
- Start Ignition gateway (if not started already)
- Open designer
- Create a Perspective view and add a label with whatever text you want in it

In the command line run the following command to view changed files:
```
git status
```
*Note: If using VScode, this is a good time to jump back into that window and show the diffs for the actual files in the source control extension

### Commit resources and push to remote repo

In the command line run the following commands to commit those resources and push to the remote repo:
```
git add .
git commit -m "Added Perspective view"
git push -u origin master
```

To view the localrepo as up to date run the command:
```
git status
```

Open the repo in Github to see your changes reflected there

## Part 3 - Clone to Prod environment

Move to your production environment

### Add local repo for Prod
####  Option A
Create a local repo and connect to the remote repo:
```
git init .
git add .
git commit -m "Initial commit"
git remote add origin <Repo URL>
git pull
```

#### Option B
If no environment exist yet, create the directory and clone the remote repo with the following command:
```
git clone <repo URL> <Local directory path>
```
Update env file and to match new environment

### Let's see a change all the way through!
#### Add a change to the local dev environment
Go back to the dev system and open the gateway web page.
This time let's add a programmable simulator device that users the Dairy Sim program.
Run the following commands to see what file has changed from our change, and to add and commit it to the local repo:
```
git status
git add .
git commit -m "added a programmable simulator device connection"
```

#### Push the new change to the remote repo
Let's push to the remote repo again with the following commands:
```
git push -u origin master
```
Now you can go to the remote repo and view the changes there if desired

#### Pull the new change to our prod environment
Now back on the prod environment run the following command:
git pull

## Part 4 Make change in dev environment 