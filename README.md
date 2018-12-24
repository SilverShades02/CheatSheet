# Git Hack Cheatsheet.

#### 1. Change commiter name.
* Clone the Repository.
* Goto repo dir and make a script file containing the below command.
``` bash
#!/bin/bash

git filter-branch --commit-filter '
        if [ "$GIT_COMMITTER_NAME" = "<Old Name>" ];
        then
                GIT_COMMITTER_NAME="<New Name>";
                GIT_COMMITTER_EMAIL="<New Email>";
                git commit-tree "$@";
        else
                git commit-tree "$@";
        fi' HEAD
```
* Just run the script file. push and see the changes like this.

Before
<p align="center">
 <img src="images/Before-1.png" > 
</p>

After
<p align="center">
 <img src="images/After-1.png" >
</p>
