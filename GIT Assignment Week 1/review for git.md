## Report on 
```
git init
```
to create a new repository.
- gina  ~/Documents/testproject  git init  ✔  2110
- Initialized empty Git repository in /Users/gina/Documents/testproject/.git/

"testproject" file turned into repository by "git init" 

```
git add
git commit -m "..."
```
to propose changes using abovementioned codes.
- gina  ~/Documents/testproject   master  git add .  ✔  2112
- gina  ~/Documents/testproject   master ✚  git commit -m"test 1"
- [master (root-commit) 2dc22f0] test 1
- 1 file changed, 9 insertions(+)
- create mode 100644 code.py

"testproject" was commited to HEAD using abovementioned codes. 

```
git checkout -b <branch_name>
```
to create a new branch and switch this new branch.

- gina  ~/Documents/testproject   master  git checkout -b extension
- Switched to a new branch 'extension'

A new branch named "extension" was created and switched.

```
git add <filename>
git commit -m "..."
```
to propose changes into file mentioned using "git add"
these changes can be mentioned using (git commit -m "small refer to what changed in the file")

- gina  ~/Documents/testproject   extension  git add code.py  ✔  2116
- gina  ~/Documents/testproject   extension ✚  git commit -m"new code"
- [extension 2e19aba] new code
- 1 file changed, 11 insertions(+)

```
git add remote origin <server>
```
to connect your repository to a remote server to be able to push your changes to that remote server.

- gina  ~/Documents/testproject   extension  git remote add origin https://github.com/GinaF28/testproject.git

Extension branch was connected to github server. It is ready to get push our changes to github server mentioned.

```
git push origin <branch>
```
- gina  ~/Documents/testproject   extension  g push origin extension
- to send changes to remoted server.
- Counting objects: 3, done.
- Delta compression using up to 4 threads.
- Compressing objects: 100% (2/2), done.
- Writing objects: 100% (3/3), 423 bytes | 423.00 KiB/s, done.
- Total 3 (delta 0), reused 0 (delta 0)
- remote:
- remote: Create a pull request for 'extension' on GitHub by visiting:
- remote: https://github.com/GinaF28/testproject/pull/new/extension
- remote:
- To github.com:GinaF28/testproject.git
- * [new branch] extension -> extension

the changes were sent to connected repository.

```
git branch -v
```
to 

```
git remote -v
```
to view information about the remote repository.
- gina  ~/Documents/testproject   extension  g remote -v  ✔  2136
- origin git@github.com:GinaF28/testproject.git (fetch)
- origin git@github.com:GinaF28/testproject.git (push)

```
git log
```
to wiew repository history.

```
git tag
```
to tag repository to call this repository with the tag.for example you can use that tag when you decide to execute "git push origin -tag-"!!
- gina  ~/Documents/testproject   extension  g tag version1.0

```
git status
```
to view tracked and untracked files within working tree status.
- gina  ~/Documents/testproject   extension version1.0  g status  ✔  2142
- On branch extension
- nothing to commit, working tree clean

as it looks, we have 'working tree clean' so there is no any change in repository.
- gina  ~/Documents/testproject   extension version1.0  g status  ✔  2143
- On branch extension
- Changes not staged for commit:
- (use "git add <file>..." to update what will be committed)
- (use "git checkout -- <file>..." to discard changes in working directory)

- modified: code.py
- no changes added to commit (use "git add" and/or "git commit -a")

the modified files can be seen in working tree status after changes are added using "git status"

```
git stash
```
to record the changes what you have made to working copy temporarily so you can switch branch and work on something else.
- gina  ~/Documents/testproject   extension version1.0 ●  g stash
- Saved working directory and index state WIP on extension: 2e19aba new code


```
git stash apply
```
you can reapply the changes to your working copy and keep them in your stash with "git stash apply"
- gina  ~/Documents/testproject   extension version1.0 ⍟1  g checkout master
- Switched to branch 'master'
- Your branch is up to date with 'origin/master'.
- gina  ~/Documents/testproject   master ⍟1  g stash apply
- Auto-merging code.py
- On branch master
- Your branch is up to date with 'origin/master'.
- Changes not staged for commit:
- (use "git add <file>..." to update what will be committed)
- (use "git checkout -- <file>..." to discard changes in working directory)
- modified: code.py
- no changes added to commit (use "git add" and/or "git commit -a")

Master branch was switched and the changes in the stash were reapplied to master branch.

- gina  ~/Documents/testproject   master ● ⍟1  git add .  ✔  2146
- gina  ~/Documents/testproject   master ✚ ⍟1  git commit -m"stashed adds"
- [master e7cc041] stashed adds
- Merge branch 'extension'
- 1 file changed, 2 insertions(+)
- gina  ~/Documents/testproject   master ↑1 ⍟1  git push origin master
- Counting objects: 3, done.
- Delta compression using up to 4 threads.
- Compressing objects: 100% (2/2), done.
- Writing objects: 100% (3/3), 291 bytes | 291.00 KiB/s, done.
- Total 3 (delta 1), reused 0 (delta 0)
- remote: Resolving deltas: 100% (1/1), completed with 1 local object.
- To github.com:GinaF28/testproject.git
- 2dc22f0..e7cc041 master -> master

Committed changes were pushed to remote repository.

```
git clone 
```
to clone a repository into a new directory.
- gina  ~/Documents  g clone git@github.com:TheAlgorithms/Python.git
- Cloning into 'Python'...
- remote: Enumerating objects: 1, done.
- remote: Counting objects: 100% (1/1), done.
- remote: Total 3975 (delta 0), reused 0 (delta 0), pack-reused 3974
- Receiving objects: 100% (3975/3975), 7.25 MiB | 717.00 KiB/s, done.
- Resolving deltas: 100% (2072/2072), done.

The repository was cloned into new folder name Python in Documents.

```
git merge <branch>
```
to merge another branch into active branch.
- gina  ~/Documents/testproject   master ⍟1  g merge extension  ✔  2160
- Auto-merging code.py
- Merge made by the 'recursive' strategy.
- code.py | 11 +++++++++++
- 1 file changed, 11 insertions(+)

Extension branch was merged into master branch.

```
git fetch
```
to download objects and refs from another repository.

gina  ~/Documents/testproject   master ↑2 ⍟1  g fetch origin  ✔  2161
gina  ~/Documents/testproject   master ↑2 ⍟1  g fork  ✔  2162















