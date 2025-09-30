# Git-advanced-exercise


# Part 1: Refining Git History (10 Challenges)

```

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (main)
$ git checkout -b dev
Switched to a new branch 'dev'

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ touch test{1..4}.md

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"        
git add test3.md && git commit -m "chore: Create third and fourth files"
[dev f453925] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
[dev 8a3eb7e] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[dev 9e57109] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git status
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)      
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git log
commit 9e57109f3f7a074024edf0592d1fdf4f163eb265 (HEAD -> dev)
Author: Docile123 <imbereyemasoo@gmail.com>
Date:   Tue Sep 30 22:39:28 2025 +0200

    chore: Create third and fourth files

commit 8a3eb7eeaf3e5cca60665a56e9c38cd420d83a00
Author: Docile123 <imbereyemasoo@gmail.com>
Date:   Tue Sep 30 22:39:27 2025 +0200

    chore: Create another file

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git add test4.md && git commit -m"Create fourth file"
[dev ac5eab5] Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git rebase -i HEAD~4
[detached HEAD 929129b] chore: Create second file
 Date: Tue Sep 30 22:39:27 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/dev.

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git log --oneline
baa18cb (HEAD -> dev) Create fourth file
a8ff955 chore: Create third and fourth files
929129b chore: Create second file
f453925 chore: Create initial file
58514b0 (origin/main, origin/HEAD, main) Initial commit

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git rebase -i HEAD~4
[detached HEAD 5af1a5c] chore: Create initial file and second file
 Date: Tue Sep 30 22:39:27 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/dev.

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git log --oneline
55d2aa1 (HEAD -> dev) Create fourth file
2d3f413 chore: Create third and fourth files
5af1a5c chore: Create initial file and second file
58514b0 (origin/main, origin/HEAD, main) Initial commit

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git reset 5af1a5c

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git status
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)      
        test3.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git add test3.md && git commit -m"Create the third file"
[dev 94f7279] Create the third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git add test4.md && git commit -m"Create the fourth file"
[dev 17826fd] Create the fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git log --oneline
17826fd (HEAD -> dev) Create the fourth file
94f7279 Create the third file
5af1a5c chore: Create initial file and second file
58514b0 (origin/main, origin/HEAD, main) Initial commit

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advance5 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/dev.

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git add unwanted.txt && git commit -m"Unwanted commit"
[dev ec44f15] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git rebase -i 
There is no tracking information for the current branch.
Please specify which branch you want to rebase against.
See git-rebase(1) for details.

    git rebase '<branch>'

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=<remote>/<branch> dev


user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git rebase -i HEAD~3
Successfully rebased and updated refs/heads/dev.

it-advanced-exercise (dev)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/dev.

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (ft/branch)
$ git add test5.md && git commit -m"Implemented test 5"
[ft/branch c68ddc3] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (ft/branch)
$ git log --oneline
c68ddc3 (HEAD -> ft/branch) Implemented test 5
c818322 (dev) chore: Create initial file and second file
fd4bd88 Create the third file and fourth file
58514b0 (origin/main, origin/HEAD, main) Initial commit

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (ft/branch)
$ git checkout dev
Switched to branch 'dev'

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git cherry-pick c68ddc3
[dev f6c3422] Implemented test 5
 Date: Tue Sep 30 22:55:28 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git log --graph
* commit f6c34225a48282a4c6fbc14b20b744ba139bd9a7 (HEAD -> dev)
| Author: Docile123 <imbereyemasoo@gmail.com>
| Date:   Tue Sep 30 22:55:28 2025 +0200
|
|     Implemented test 5
|
* commit c818322b7773840cf0bbd3949d2b404eae7beb39
| Author: Docile123 <imbereyemasoo@gmail.com>
| Date:   Tue Sep 30 22:39:27 2025 +0200
|
|     chore: Create initial file and second file
|
* commit fd4bd88e1e0055800a4d69c8f1a46fc97ba5a62b
| Author: Docile123 <imbereyemasoo@gmail.com>
| Date:   Tue Sep 30 22:43:32 2025 +0200
|

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
c818322 HEAD@{3}: checkout: moving from dev to ft/branch
c818322 HEAD@{4}: rebase (finish): returning to refs/heads/dev
c818322 HEAD@{5}: rebase (pick): chore: Create initial file and second file
fd4bd88 HEAD@{6}: rebase (pick): Create the third file and fourth file
58514b0 (origin/main, origin/HEAD, main) HEAD@{7}: rebase (start): checkout HEAD~2
aed6d1b HEAD@{8}: rebase (finish): returning to refs/heads/dev
aed6d1b HEAD@{9}: rebase (start): checkout HEAD~3
ec44f15 HEAD@{10}: commit: Unwanted commit
aed6d1b HEAD@{11}: rebase (finish): returning to refs/heads/dev
aed6d1b HEAD@{12}: rebase (squash): Create the third file and fourth file

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$

```
# Part 2: Branching Basics (10 Challenges)
```
user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git status
On branch dev
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git add README.md 

On branch dev
nothing to commit, working tree clean

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (ft/new-feature)
$ git checkout dev
Switched to branch 'dev'

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git add readme.txt && git commit -m"Updated project readme"
[dev 7bb4cfc] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git merge ft/new-feature
Merge made by the 'ort' strategy.
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git branch -D ft/new-feature
Deleted branch ft/new-feature (was 69b58e1).

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git log --oneline
8886cd8 (HEAD -> dev) Merge branch 'ft/new-feature' into dev
7bb4cfc Updated project readme
69b58e1 Implemented core functionality for new feature
e22b8d7 Add the git commands of the first challenge in readme file    
f6c3422 Implemented test 5
c818322 chore: Create initial file and second file
fd4bd88 Create the third file and fourth file
58514b0 (origin/main, origin/HEAD, main) Initial commit

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git checkout -b ft/new-branch-from-commit 69b58e1
Switched to a new branch 'ft/new-branch-from-commit'

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (ft/new-branch-from-commit)
$ git checkout dev
Switched to branch 'dev'

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git merge ft/new-branch-from-commit
Already up to date.

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (ft/new-branch-from-commit)
$ git rebase dev
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (ft/new-branch-from-commit)
$ git checkout dev
Switched to branch 'dev'

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git log --oneline
8886cd8 (HEAD -> dev, ft/improved-branch-name) Merge branch 'ft/new-feature' into dev
7bb4cfc Updated project readme
69b58e1 Implemented core functionality for new feature
e22b8d7 Add the git commands of the first challenge in readme file    
f6c3422 Implemented test 5
c818322 chore: Create initial file and second file
fd4bd88 Create the third file and fourth file
58514b0 (origin/main, origin/HEAD, main) Initial commit

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise (dev)
$ git checkout 69b58e1
Note: switching to '69b58e1'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
ay
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 69b58e1 Implemented core functionality for new feature

user@LAPTOP-31B23MFI MINGW64 ~/Desktop/New folder/revision/Git-advanced-exercise ((69b58e1...))
$

```