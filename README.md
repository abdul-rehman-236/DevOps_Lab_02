# DevOps_Lab_02
This is lab 2 below.  
1. Initialize an empty local git repo
2. Perform labs present in Lecture 2 slide 7
3. Perform labs present in Lecture 2 slide 10
4. Perform labs present in Lecture 2 slide 11
5. Perform labs present in Lecture 2 slide 12
6. Perform labs present in Lecture 2 slide 13
7. Perform labs present in Lecture 2 slide 15
8. Perform labs present in Lecture 2 slide 17
9. Perform labs present in Lecture 3 slide 3

### 1: Initialize an empty local git repo
 The command for initializing an empty local git repository is:  
  > git init

### 2: Perform labs present in Lecture 2 slide 7
* Create file1.txt and file2.txt in the project
  > touch file1.txt file2.txt
* git add file1.txt and file2.txt
  > git add file1.txt file2.txt
* git status  
  Note: file1.txt and file2.txt are added to staging area.
  ```
  On branch master
  Your branch is up to date with 'origin/master'.

  Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
          new file:   file1.txt
          new file:   file2.txt

  Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   README.md
* git ls-files (to check which files are there in staging area)
  ```
  README.md
  file1.txt
  file2.txt
* git commit -m "1st commit"
  ```
  [master 4c77bd1] 1st commit
  2 files changed, 0 insertions(+), 0 deletions(-)
  create mode 100644 file1.txt
  create mode 100644 file2.txt
* git status (Now file1.txt and file2.txt are no longer in staging area. They are moved to local git repo)
  ```
  On branch master
  Your branch is ahead of 'origin/master' by 1 commit.
    (use "git push" to publish your local commits)

  Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   README.md

  no changes added to commit (use "git add" and/or "git commit -a")
* Make change to file1
  ```
  nano file1.txt      #will open file1.txt in nano editor. Do you changes in this.

  # As I write
  This is first line.
  This is the second line.
* git add file1.txt
  > git add file1.txt
* git commit –m "2nd commit"
  ```
  [master 04e0344] 2nd commit
  1 file changed, 2 insertions(+)
* Delete file2
  > rm file2.txt
* git add file2.txt
  This will remove file2.txt from un staging area and move it to staging area.
  ```
  git status
  On branch master
  Your branch is ahead of 'origin/master' by 2 commits.
    (use "git push" to publish your local commits)

  Changes not staged for commit:
    (use "git add/rm <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   README.md
          deleted:    file2.txt

  no changes added to commit (use "git add" and/or "git commit -a")


  git add file2.txt  


  git status
  On branch master
  Your branch is ahead of 'origin/master' by 2 commits.
    (use "git push" to publish your local commits)

  Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
          deleted:    file2.txt

  Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   README.md
* git commit -m "3rd commit"  
  This will remove file2.txt from staged area to the local repository.
  ```
  [master 42ca3b1] 3rd commit
  1 file changed, 0 insertions(+), 0 deletions(-)
  delete mode 100644 file2.txt
* git commit -a -m "this will skip the staging area, not recommended".  
  **Note: We don't add README.md to staging area. It directly moves to local repo.**
  ```
  git status
  On branch master
  Your branch is ahead of 'origin/master' by 3 commits.
    (use "git push" to publish your local commits)

  Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   README.md

  no changes added to commit (use "git add" and/or "git commit -a")


  git commit -a -m "this will skip the staging area, not recommended"
  1 file changed, 123 insertions(+), 1 deletion(-)


  git status
  On branch master
  Your branch is ahead of 'origin/master' by 4 commits.
    (use "git push" to publish your local commits)

  nothing to commit, working tree clean
### Point 3: Perform labs present in Lecture 2 slide 10
  * To remove a file we need to delete it from our working directory and staging area. For following practice `file.txt should already present in remote repo`.
    * One way to do this
      ```
      rm file.txt              # Deletes the file from the working directory


      git status
      On branch master
      Your branch is up to date with 'origin/master'.

      Changes not staged for commit:
        (use "git add/rm <file>..." to update what will be committed)
        (use "git restore <file>..." to discard changes in working directory)
              modified:   README.md
              deleted:    file.txt

      no changes added to commit (use "git add" and/or "git commit -a")


      git add file.txt         # Marks the deletion in Git (staging the change)


      git status
      On branch master
      Your branch is up to date with 'origin/master'.

      Changes to be committed:
        (use "git restore --staged <file>..." to unstage)
              deleted:    file.txt

      Changes not staged for commit:
        (use "git add <file>..." to update what will be committed)
        (use "git restore <file>..." to discard changes in working directory)
              modified:   README.md
    * Another way to do this
      ```
      git rm file.txt          # It removes file from both working directory and Marks the deletion in Git (staging the change) in one step.


      git status
      On branch master
      Your branch is up to date with 'origin/master'.

      Changes to be committed:
        (use "git restore --staged <file>..." to unstage)
              deleted:    file.txt

      Changes not staged for commit:
        (use "git add <file>..." to update what will be committed)
        (use "git restore <file>..." to discard changes in working directory)
              modified:   README.md
    * Another way to do this
      ```
      git rm --cached -r file1.txt         # This will remove file1.txt from staging area but not from working directory
      # -r (recursive) allows you to remove directories.


      git status
      On branch master
      Your branch is up to date with 'origin/master'.

      Changes to be committed:
        (use "git restore --staged <file>..." to unstage)
              deleted:    file.txt

      Changes not staged for commit:
        (use "git add <file>..." to update what will be committed)
        (use "git restore <file>..." to discard changes in working directory)
              modified:   README.md

      Untracked files:
        (use "git add <file>..." to include in what will be committed)
              file.txt

* For renaming
  * One way to do this
    ```
    mv file.txt filenew.txt        # file.txt would be unstaged and filenew.txt would be untracked.


    git status
    On branch master
    Your branch is up to date with 'origin/master'.

    Changes not staged for commit:
      (use "git add/rm <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   README.md
            deleted:    file.txt

    Untracked files:
      (use "git add <file>..." to include in what will be committed)
            filenew.txt

    no changes added to commit (use "git add" and/or "git commit -a")

    git ls-files
    git add file.txt filenew.txt     # To stage both files


    git status
    On branch master
    Your branch is up to date with 'origin/master'.

    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            renamed:    file.txt -> filenew.txt

    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   README.md
  * Another way to do this
    ```
    git mv file.txt filenew.txt       # Rename file.txt to filenew.txt and add to staging area in one step.


    git status
    On branch master
    Your branch is up to date with 'origin/master'.

    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            renamed:    file.txt -> filenew.txt

    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   README.md
</pre>

### Point 4: Perform labs present in Lecture 2 slide 11
* Create a .gitignore file
  > nano .gitignore                      # This will create .gitignore file. Type file.txt in it to ignore it by Git. Save and close the .gitignore.  
  git add .gitignore  
  git commit -m 'Add .gitignore'  
  git push
  
  If you come from _Point 3_ exercise here, You might wonder file.txt is still tracked by Git, although added to .gitignore. The reason is **_.gitignore_ only prevents untracked files from being added—it does not remove files that are already tracked.**.  
  So to prevent it from being tracked, You must remove it from remote repo. Perform the following steps.
  ```
  git rm --cached file.txt
  git commit -m 'Prevent file.txt from being tracked'
  git push

### 5: Perform labs present in Lecture 2 slide 12

* create file1 and file2
  > touch file1 file2
* git status -s
  > M README.md  
  > ?? file1  
  > ?? file2
* git add file1
  > This will add file1 to staging area.
* git status -s
  > M README.md  
  > A  file1  
  > ?? file2
* Make changes to file1
  > nano file1  
  > Let say write 'This is content of file1'. Save and Exit the file1.
* git status -s
  > M README.md  
  > AM file1  
  > ?? file2
* add file1
  > git add file1  
  > This add file1 to staging area
* git status -s
  > M README.md  
  > A  file1  
  > ?? file2
* Make another change to file1
  > nano file1  
  > Let say modify 'This is content of file1' to 'This is the modified content of file1'. Save and Exit the file1.
* git status –s
  > M README.md  
  > AM file1  
  > ?? file2
* git add file1 file2
  > This will add both file1 and file2 to staging area.
* git status -s
  > M README.md  
  > A  file1  
  > A  file2

### 6: Perform labs present in Lecture 2 slide 13

* git status
  ```
  On branch master
  Your branch is up to date with 'origin/master'.

  Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
          new file:   file1
          new file:   file2

  Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   README.md
* git diff
  ```
  diff --git a/README.md b/README.md
  index 34b5ba4..098c8cc 100644
  --- a/README.md
  +++ b/README.md
  @@ -111,13 +111,237 @@ This is lab 2 below.
    [master 42ca3b1] 3rd commit
    1 file changed, 0 insertions(+), 0 deletions(-)
    delete mode 100644 file2.txt
  +* git commit -a -m "this will skip the staging area, not recommended".  
  diff --git a/README.md b/README.md
  index 34b5ba4..098c8cc 100644
  --- a/README.md
  +++ b/README.md
  @@ -111,13 +111,237 @@ This is lab 2 below.
    [master 42ca3b1] 3rd commit
    1 file changed, 0 insertions(+), 0 deletions(-)
    delete mode 100644 file2.txt
  +* git commit -a -m "this will skip the staging area, not recommended".  
  +  **Note: We don't add README.md to staging area. It directly moves to local repo.**
  +  ```
  diff --git a/README.md b/README.md
  index 34b5ba4..098c8cc 100644
  --- a/README.md
  +++ b/README.md
  @@ -111,13 +111,237 @@ This is lab 2 below.
    [master 42ca3b1] 3rd commit
    1 file changed, 0 insertions(+), 0 deletions(-)
    delete mode 100644 file2.txt
  +* git commit -a -m "this will skip the staging area, not recommended".  
  +  **Note: We don't add README.md to staging area. It directly moves to local repo.**
  +  ```
  +  git status
  +  On branch master

  .....
  .....
* git diff --staged
  ```
  diff --git a/file1 b/file1
  new file mode 100644
  index 0000000..3f6d66e
  --- /dev/null
  +++ b/file1
  @@ -0,0 +1 @@
  +This is modified content of file1
  diff --git a/file2 b/file2
  new file mode 100644
  index 0000000..e69de29
  
### Point 7: Perform labs present in Lecture 2 slide 15

* git log
  ```
  commit 7d4aadef8e2656b1aaae1aadebfd3182462ed15d (HEAD -> master, origin/master, origin/HEAD)
  Author: Abdul <abdul.rehman.3091149236@gmail.com>
  Date:   Fri Apr 4 09:27:56 2025 -0700

      Add gitignore

  commit 7fede00388cef6b3267ae52a039c7cfecdc755b3
  Author: Abdul <abdul.rehman.3091149236@gmail.com>
  Date:   Fri Apr 4 09:05:32 2025 -0700

      Add file.txt

  commit 8d8ece2f71bcbc4b09c40cb33eac2aa5af06e3f1
  Author: Abdul <abdul.rehman.3091149236@gmail.com>
  Date:   Thu Apr 3 06:54:32 2025 -0700

      this will skip the staging area, not recommended

  commit 42ca3b12d1684f280b90cebb16f03c9142ca3705
  Author: Abdul <abdul.rehman.3091149236@gmail.com>
  Date:   Thu Apr 3 06:51:55 2025 -0700

      3rd commit

  commit 04e03440ef954b1e47b7af36da3f78f274d88018
  Author: Abdul <abdul.rehman.3091149236@gmail.com>
  Date:   Thu Apr 3 06:47:58 2025 -0700

      2nd commit

  commit 4c77bd1d43920096dcf5fd818f637deda06cf765
  Author: Abdul <abdul.rehman.3091149236@gmail.com>
  Date:   Thu Apr 3 06:41:14 2025 -0700

      1st commit

  commit 75dc22ee5120972b110b0e315122a53549a5014e
  Author: Abdul Rehman <abdul.rehman.3091149236@gmail.com>
  Date:   Thu Apr 3 05:56:29 2025 -0700

      Initial commit
* git log --oneline
  ```
  7d4aade (HEAD -> master, origin/master, origin/HEAD) Add gitignore
  7fede00 Add file.txt
  8d8ece2 this will skip the staging area, not recommended
  42ca3b1 3rd commit
  04e0344 2nd commit
  4c77bd1 1st commit
  75dc22e Initial commit
* git log --oneline  --reverse
  ```
  75dc22e Initial commit
  4c77bd1 1st commit
  04e0344 2nd commit
  42ca3b1 3rd commit
  8d8ece2 this will skip the staging area, not recommended
  7fede00 Add file.txt
  7d4aade (HEAD -> master, origin/master, origin/HEAD) Add gitignore

### Point 8: Perform labs present in Lecture 2 slide 17

* git restore --staged file1
  ```
  Alternatives:
  1) git restore --cached file1
  2) git reset HEAD file1
  
  These commands will unstaged the file1 and move to untracked area.

  git status
  On branch master
  Your branch is up to date with 'origin/master'.

  Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
          new file:   file2

  Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   README.md

  Untracked files:
    (use "git add <file>..." to include in what will be committed)
          file1

### Point 9: Perform labs present in Lecture 3 slide 3

* git stash
  ```
  git status
  On branch master
  Your branch is up to date with 'origin/master'.

  Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
          new file:   file2

  Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   README.md

  Untracked files:
    (use "git add <file>..." to include in what will be committed)
          file1


  git stash                # With add changes to stash stack


  git status
  On branch master
  Your branch is up to date with 'origin/master'.

  Untracked files:
    (use "git add <file>..." to include in what will be committed)
          file1

  nothing added to commit but untracked files present (use "git add" to track)
* git stash pop
  ```
  # This will pop out last stack from stash stacks


  On branch master
  Your branch is up to date with 'origin/master'.

  Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
          new file:   file2

  Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
          modified:   README.md

  Untracked files:
    (use "git add <file>..." to include in what will be committed)
          file1

  Dropped refs/stash@{0} (a733561f0789b99a3a150cc8593dd6b6246484f4)
* git stash clear
  ```
  Remove all stash stack items
* git stash list
  ```
  Enlist all stash stack items
* git stash-drop a733561f0789b99a3a150cc8593dd6b6246484f4
  ```
  Remove stash item with hash a733561f0789b99a3a150cc8593dd6b6246484f4