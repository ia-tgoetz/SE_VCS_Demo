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
''''git init .''''
Then run add the remote repo:
''''git remote add origin https://github.com/ia-akoch/SE_VCS_Demo''''
Next add the locally tracked files and commit them to the local repo
''''