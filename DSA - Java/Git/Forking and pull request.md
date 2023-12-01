
Next Topic : [[Squashing]]

- Getting a public repo code into your account , so that you can modify it from you account 
- You must fork a repo before you make any changes on other's repo
- To know about forking watch video from 38 Min
- Once you make the changes , the authorized owner of the project can verify and merge your forked repo into his repo , so that everybody can see that 


### Upstream URL 

- Origin url is where the repo that is in your account 
- upstream url is where the original repo of the project owner
#### Adding upstream url

```
git remote add upstream url_of_the_original_repo
```

### Pull request

Request the original branch or Original repo owner to accept the changes made that we made in the forked repo or other branch to accept the changes into the original branch or repo 


### It is always recommended to create a new branch for all the feature or a bug , so that a single pull request doesn't have many line or codes. It is always okie to have 100 or more branched but not the single pr managing more than 1 feature or a bug


### In case you want to remove the last commit from the git history

Step 1
```
git reset commit_code 
```
Step 2 
```
git add 
git commit
git stash
```

So that the last commit you made have to removed moved to the stash now 

Step 3
```
git push origin branch_name -f
```
-f is nothing but it is a forced push as it modifies the commit stored in the online repo

### In case your higher upstream branch is ahead of your branch

```
git pull upstream main
```
This pulls all the code from the main branch of original repo 


This pulled code is still in your local computer repo , you need to push it to your online repo

```
git push origin branch_name
```

#### For this process , there is a easy way in git hub on a single click

![[Pasted image 20231201142147.png]]
That Fetch upstream button , gets all the ahead code from upstream branch


