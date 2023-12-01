Next Topic : [[Branches]] 

- "ls" for listing the diretories in the folder
- "ls -a" list all the folders including the hidden folders
- "mkdir" to make a new folder 
- "cd" for changing the directory 
- "touch filename" for creating the file or folder


# Git commands

#### Git init

- ``git init`` It initialize an empty git repository
- Any changes made inside the repository are noted 
#### Git status
- ``git status`` :: This basically says status of files that are tracking , not tracking , commited files

![[Pasted image 20231201111348.png]]

#### Git add 

- ``git add`` :: git add is used to set the file to the tracking stage
- ``git add .`` :: adds all the untracked files from the folder
- ``git add filename  filename`` :: adds the only folder that you have named near add

#### Git commit 

- ``git commit -m "your message"`` for saving the progress of that file for the past edits

![[Pasted image 20231201112454.png]]

Once after making a commit , status will be cleared
Don't worry about the other stuffs

#### Git status after modification

- If you make any changes in the file , the modified file will be displayed
![[Pasted image 20231201113812.png]]

- After executing the "git add ."
![[Pasted image 20231201113936.png]]

#### git restore 

- ``git restore --staged filename`` is used to restore the last "git add" command

![[Pasted image 20231201114207.png]]

- ``git add .``
- ``git commit -m 'filename modified'``

![[Pasted image 20231201114331.png]]
- The 1 file changed is no of files that are added using the command ``git add .``
- The 3 insertions are the no of lines modified in the files that are changed

#### Git log 

- ``git log`` is used to view the history of the project 

![[Pasted image 20231201114554.png]]

#### Git status 

- Once you delete the file it make it as 

![[Pasted image 20231201114737.png]]

#### Git reset

Once you need to restore or cancel the commit you made in the past you need to execute the command ``git log``

Copy the commit code of the stage you need to go back , and execute the 

``git reset commit_code``

![[Pasted image 20231201115330.png]]

#### Git stash

This is used to hide some action from showing to the history , 
- When we no need to commit the changes and also should not lose the code or the modification we can use it to hide from the history and can bring back when we need it

- ``git add .``
- ``git stash``

![[Pasted image 20231201120246.png]]

once you need the codes that are stash back you need to execute the ``stash pop``

![[Pasted image 20231201120431.png]]

when you no need the stashed code back you can remove those stash

- ``git stash clear``

### Starting a repo

- After creating a repo , copy the link and execute 
	 ``git remote add origin repo_link``

- This will make the folder as it's repo files 
	 ``git push origin master
	 Here , 
	 -  push is command keyword to push into repo
	 -  origin is command keyword to push that into the origin repo that is linked
	 -  master is that can be replaced with your specific branch in which you need to push it
	 
 This is used to push all the modifications and commits to the git hub online repo