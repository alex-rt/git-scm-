-CHAPTER 2

-Initializate a repository

$ git init
$ git add *.c
$ git add LICENSE
$ git commit -m 'initial project version'

-Cloning a repository
$ git clone https://github.com/libgit2/libgit2
$ git clone https://github.com/libgit2/libgit2 mylibgit

-Checking your files´ state
$ git status
$ echo 'My Project' > README
$ git status

-Track new files
$ git add README
$ git status

-Prepare modified files
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

$ git add CONTRIBUTING.md
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

$ vim CONTRIBUTING.md
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

$ git add CONTRIBUTING.md
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

-Abbreviaded state
$ git status -s
 M README
MM Rakefile
A  lib/git.rb
M  lib/simplegit.rb
?? LICENSE.txt

-Ignore files
$ cat .gitignore
*.[oa]
*~

-See prepared and unprepared changes
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

$ git diff --staged
diff --git a/README b/README
new file mode 100644
index 0000000..03902a1
--- /dev/null
+++ b/README
@@ -0,0 +1 @@
+My Project
$ git add CONTRIBUTING.md
$ echo 'test line' >> CONTRIBUTING.md
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

-Confirm changes
$ git commit

-Remove files
$ rm PROJECTS.md
$ git status

$ git rm PROJECTS.md
rm 'PROJECTS.md'
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

-Change file name
$ git mv file_from file_to
$ git mv README.md README
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

-Another way to do that:
$ mv README.md README
$ git rm README.md
$ git add README

-Confirmation history
$ git log

-History limits
$ git log --since=2.weeks

-Undo things
$ git commit –amend
$ git commit -m 'initial commit'
$ git add forgotten_file
$ git commit –amend
-Undo a prepared file
$ git add .
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

$ git reset HEAD CONTRIBUTING.md
Unstaged changes after reset:
M	CONTRIBUTING.md
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   CONTRIBUTING.md
-Undo a modified file
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   CONTRIBUTING.md
$ git checkout -- CONTRIBUTING.md
$ git status

-See your remote
$ git clone https://github.com/schacon/ticgit
$ cd ticgit
$ git remote
origin

-URLs associated to the name:
$ git remote -v

-Add remote repository
$ git remote
origin
$ git remote add pb https://github.com/paulboone/ticgit
$ git remote -v

-Using pb instead of the full url
$ git fetch pb

-Bring and combine remotes:
$ git fetch [remote-name]

-Send your remotes
$ git push origin master

-Inspect a remote
$ git remote show origin

-Remove and rename remotes
$ git remote rename pb paul
$ git remote
$ git remote rm paul
$ git remote

-List of tags
$ git tag

-Search tags
$ git tag -l 'v1.8.5*'

-Tags with annotations
$ git tag -a v1.4 -m 'my version 1.4'

-Light tags
$ git tag v1.4-lw

-Late tagging
$ git tag -a v1.2 9fceb02

-Share tags
$ git push origin v1.5

-Tag check out
$ git checkout -b version2 v2.0.0

-Git Alias
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
$ git config --global alias.unstage 'reset HEAD --'
$ git unstage fileA
$ git reset HEAD fileA
$ git config --global alias.last 'log -1 HEAD'
$ git config --global alias.visual "!gitk"
