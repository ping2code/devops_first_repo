

NOTE:\*\*\* Make sure both VSCode and Git bash are working in same directory



=====================> **git basic to push files to git** <========================



git status

git add README.md

git status

git commit -m "feat: first change in README.md"

git push

git log --oneline



=====================> **git branch commands**  <===================================



git branch

git branch -a

git checkout <branch\_name> or git switch <branch\_name>



Creating branch using git bash:



git branch <branch\_ame>  -->  to create new branch via git bash

git checkout -b <branch\_name> --> to create and switch to new branch single command

git switch -c feature-readme

create files

git add <files>

git status

git commit -m "feat:xxxxxxx"

git push





Push files from custom to main branch:



=====================> **git reset --mixe**d <==================================



git reset:



git reset (--soft --mixed --force)



e.g:

$ git log --oneline

298625d (HEAD -> third\_branch, origin/third\_branch) feat: Added new Feature 5 and 6

0e2b38d feat: Added new Feature 4

8ab9227 feat: Added new Feature 3

0ae26cb feat: Added new Feature 2

ad99749 feat: added new feature 1

47465d1 doc: added new document

e68afef feat: Added second notes to the README

6e85a03 feat: first change in README.md

235a54f Initial commit



to remove/reset the changes to previous

\*\*\*Need to use the previous commit has to reset latest one

e.g: 0e2b38d to be used in order to delete the files commited under 298625d







\--mixed is the default option, until unless you specify other options 



git reset --mixed 0e2b38d

next 

git push  -->  will not remove/reset the files are changes 



$ git push

To https://github.com/ping2code/devops\_first\_repo.git

&#x20;! \[rejected]        third\_branch -> third\_branch (non-fast-forward)

error: failed to push some refs to 'https://github.com/ping2code/devops\_first\_repo.git'



$git push -f



=====================> **git reset ----soft** <==================================

\--soft option will keep the file in staging area (which is equal to (git add is done), where --mixed with remove the file from staging area )

we just removing commit of the file using git reset --soft



$ git status

On branch third\_branch

Your branch is up to date with 'origin/third\_branch'.



Changes to be committed:

&#x20; (use "git restore --staged <file>..." to unstage)  <-------------------------------

&#x20;       new file:   feature-4.txt



Untracked files:

&#x20; (use "git add <file>..." to include in what will be committed)

&#x20;       feature-5.txt

&#x20;       feature-6.txt



=====================> **git reset --hard** <==================================



git reset --hard   (Note: very dangerous option which will not keep the files in staging area like --soft option, and completely delete the all files from staging area in the branch )



git reset --hard 0ae26cb



$ git status

On branch third\_branch

Your branch is behind 'origin/third\_branch' by 1 commit, and can be fast-forwarded.

&#x20; (use "git pull" to update your local branch)



Untracked files:

&#x20; (use "git add <file>..." to include in what will be committed)

&#x20;       feature-5.txt

&#x20;       feature-6.txt



nothing added to commit but untracked files present (use "git add" to track)



$ git push -f

Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)

To https://github.com/ping2code/devops\_first\_repo.git

&#x20;+ 8ab9227...0ae26cb third\_branch -> third\_branch (forced update)







=====================> **git commit --amend** <==================================



To modify the commit message from the list of commit hashes



Before:

sirii@LUCKYTHEWINNER MINGW64 /f/MyRepos/devops\_first\_repo (third\_branch)

$ git log --oneline

0ae26cb (HEAD -> third\_branch, origin/third\_branch) feat: Added new Feature 2

ad99749 feat: added new feature 1





after:

$ git log --oneline

3eb7022 (HEAD -> third\_branch) feat: Added new Feature 2 for demo

ad99749 feat: added new feature 1



=====================> **git commit --amend using existing commit hash** <==================================



git commit --amend  (commit message changed to --> (**feat: Added new Feature 2 for demo as new file second time)**


Now modify the actual file content.

then 
git add <file name>

git push


=====================> **git cherry-pick <commit-hash>** <==================================



To pick a feature from one branch to other

git cherry-pick <commit-hash>

Branch1 									Branch2
feature-1.txt									Feature-1.txt
feature-2.txt									feature-2.txt
feature-4.txt				
             <<<<<-----<<<<<<---------|
                                      |------------------<<<<<<<----------------feature-3.txt















































































































































