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

git commit -a -m "this will skip the staging area, not recommended"
</pre>
3- Perform labs present in Lecture 2 slide 10
4- Perform labs present in Lecture 2 slide 11
5- Perform labs present in Lecture 2 slide 12
6- Perform labs present in Lecture 2 slide 13
7- Perform labs present in Lecture 2 slide 15
8- Perform labs present in Lecture 2 slide 17
9- Perform labs present in Lecture 3 slide 3