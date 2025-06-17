
Next Topic : [[Forking and pull request]]

Branches are a separate copy of the code , that separate code are used by the other external dev , so that the original code is not disturbed and once the dev's code is verified , it can be merged with the original branch (default branch)


#### Create a branch
- ``git branch branch_name`` - to create a branch

#### Listing branches
- ``git branch -r`` 
#### Into the branch 
- ``git chechout branch_name`` - to enter the branch , So that your next push command is into that branch

### Image representation of Branch

```
git commit 
git commit 
git commit 
git commit 
```
After these commits your git's image representation will be like this

![[Pasted image 20231201134042.png]]

```
git branch feature
```

![[Pasted image 20231201134202.png]]

```
Git checkout feature
```
After executing this , the head `*` will move to the feature 

![[Pasted image 20231201134313.png]]

```
git commit 
git commit 
```

![[Pasted image 20231201134351.png]]

```
git checkout main
git commit 
```

![[Pasted image 20231201134438.png]]

```
git merge feature
```

![[Pasted image 20231201134512.png]]


