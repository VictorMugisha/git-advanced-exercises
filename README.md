
# Advanced Git Exercises

## Part 1: Refining Git History (10 Challenges)

### This section includes the bash history for all Part 1 Challenges
```bash 
victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ touch test{1..4}.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test1.md && git commit -m "chore: Create initial file"
[main (root-commit) fe53acf] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)       
 create mode 100644 test1.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test2.md && git commit -m "chore: Create another file"
[main 06aea15] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test3.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test3.md && git commit -m "chore: Create third and fourth files"
[main 8142256] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test4.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit --amend -m "chore: Created fourth file"
[main 08dce53] chore: Created fourth file
 Date: Tue May 21 08:10:40 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
# These lines can be re-ordered; they are executed from top to bottom.
chore: Create second file
$ git log
commit 08dce53ff32168cde7e7d538271024468dd00e1c (HEAD -> main)
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:10:40 2024 +0200

    chore: Created fourth file

commit 06aea1582f5a642f2565ba6da49182f22b0b890d
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:10:03 2024 +0200

    chore: Create another file

commit fe53acf0774175c49e0903ebfe385f485a1a5b11
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:10:02 2024 +0200

    chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase HEAD~2
Current branch main is up to date.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~2
[detached HEAD 723f260] chore: Create second file
 Date: Tue May 21 08:10:03 2024 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase --continue
fatal: No rebase in progress?

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git status
On branch main
nothing to commit, working tree clean
pick 723f260 chore: Create second file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log
commit 80568e99468e1427a372bbc34ffdbaa27f9c78e3 (HEAD -> main)
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:10:40 2024 +0200

    chore: Created fourth file
pick 723f260 chore: Create second file
# This is a combination of 2 commits.

commit 723f2600477339763d58e65320479b957a43ea50
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:10:03 2024 +0200

    chore: Create second file

commit fe53acf0774175c49e0903ebfe385f485a1a5b11
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:10:02 2024 +0200

    chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
80568e9 (HEAD -> main) chore: Created fourth file
723f260 chore: Create second file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~3
fatal: invalid upstream 'HEAD~3'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~3
fatal: invalid upstream 'HEAD~3'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~2
[detached HEAD 9e5058b] Create a squash of two commits
 Date: Tue May 21 08:10:03 2024 +0200
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log
commit 9e5058bfa370b1356e3e34327cb032f91b17d25c (HEAD -> main)
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:10:03 2024 +0200

    Create a squash of two commits

    chore: Create second file

    chore: Created fourth file

commit fe53acf0774175c49e0903ebfe385f485a1a5b11
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:10:02 2024 +0200

    chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
9e5058b (HEAD -> main) Create a squash of two commits
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git reset HEAD~1

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test2.md
        test3.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test2.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m 
error: switch `m' requires a value

pick e2a0e36 chore: Added test3.md file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "chore: Added test2.md file"
[main 692f0c0] chore: Added test2.md file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test3.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "chore: Added test3.md file"
[main e2a0e36] chore: Added test3.md file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test4.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "chore: Added test4.md file"
[main 8a3c3a4] chore: Added test4.md file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
8a3c3a4 (HEAD -> main) chore: Added test4.md file
e2a0e36 chore: Added test3.md file
692f0c0 chore: Added test2.md file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~2
[detached HEAD bc6e197] Created third and fourth files
 Date: Tue May 21 08:36:44 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
drop bc6e197 Created third and fourth files
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
bc6e197 (HEAD -> main) Created third and fourth files
692f0c0 chore: Added test2.md file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add unwanted.text

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "Unwanted commit"
[main 35ef26f] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.text

drop 692f0c0 chore: Added test2.md file
victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
35ef26f (HEAD -> main) Unwanted commit
bc6e197 Created third and fourth files
692f0c0 chore: Added test2.md file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~2
drop 8a8cdff Unwanted commit
Successfully rebased and updated refs/heads/main.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log
commit e2385aeba9b39769aee385851393e280e313fcb7 (HEAD -> main)
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:40:43 2024 +0200

    Unwanted commit

commit 692f0c0465810269a32aa987beb3a6a44032661c
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:36:28 2024 +0200

    chore: Added test2.md file

commit fe53acf0774175c49e0903ebfe385f485a1a5b11
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:10:02 2024 +0200

    chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
8a8cdff (HEAD -> main) Unwanted commit
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~1
Successfully rebased and updated refs/heads/main.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log
commit fe53acf0774175c49e0903ebfe385f485a1a5b11 (HEAD -> main)
Author: Victor Mugisha Shyaka <victormugishavm6@gmail.com>
Date:   Tue May 21 08:10:02 2024 +0200

    chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ touch test{2..4}.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add .

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git reset

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test2.md
        test3.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test2.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "chore: Created second file"
[main 826ff47] chore: Created second file
 1 file changed, 0 insertions(+), 0 deletions(-)

 create mode 100644 test2.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test3.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "chore: Created third file"
[main 903efce] chore: Created third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test4.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "chore: Created fourth file"
[main 8526556] chore: Created fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
8526556 (HEAD -> main) chore: Created fourth file
903efce chore: Created third file
826ff47 chore: Created second file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~4
fatal: invalid upstream 'HEAD~4'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git rebase -i HEAD~3
Successfully rebased and updated refs/heads/main.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
877033a (HEAD -> main) chore: Created fourth file
d79a89a chore: Created second file
d514fc7 chore: Created third file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ echo "Some content here" > test5.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ add test5.md
bash: add: command not found

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ git add test5.md
warning: in the working copy of 'test5.md', LF will be replaced by CRLF the next time Git touches it

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ git commit -m "Implementes test5.md"
[ft/branch f7b9a0b] Implementes test5.md
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ git log --oneline
f7b9a0b (HEAD -> ft/branch) Implementes test5.md
877033a (main) chore: Created fourth file
d79a89a chore: Created second file
d514fc7 chore: Created third file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ git checkout main
Switched to branch 'main'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline ft/branch
f7b9a0b (ft/branch) Implementes test5.md
877033a (HEAD -> main) chore: Created fourth file
d79a89a chore: Created second file
d514fc7 chore: Created third file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git cherry-pick f7b9a0b
[main 69b5e8f] Implementes test5.md
 Date: Tue May 21 08:53:00 2024 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
69b5e8f (HEAD -> main) Implementes test5.md
877033a chore: Created fourth file
d79a89a chore: Created second file
d514fc7 chore: Created third file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git reflog
69b5e8f (HEAD -> main) HEAD@{0}: cherry-pick: Implementes test5.md
877033a HEAD@{1}: checkout: moving from ft/branch to main
f7b9a0b (ft/branch) HEAD@{2}: commit: Implementes test5.md
877033a HEAD@{3}: checkout: moving from main to ft/branch
877033a HEAD@{4}: rebase (finish): returning to refs/heads/main
877033a HEAD@{5}: rebase (pick): chore: Created fourth file
d79a89a HEAD@{6}: rebase (pick): chore: Created second file
d514fc7 HEAD@{7}: rebase (pick): chore: Created third file
fe53acf HEAD@{8}: rebase (start): checkout HEAD~3
8526556 HEAD@{9}: commit: chore: Created fourth file
903efce HEAD@{10}: commit: chore: Created third file
826ff47 HEAD@{11}: commit: chore: Created second file
fe53acf HEAD@{12}: reset: moving to HEAD
fe53acf HEAD@{13}: rebase (finish): returning to refs/heads/main
fe53acf HEAD@{14}: rebase (start): checkout HEAD~1
8a8cdff HEAD@{15}: rebase (finish): returning to refs/heads/main
8a8cdff HEAD@{16}: rebase (pick): Unwanted commit
fe53acf HEAD@{17}: rebase (start): checkout HEAD~2
e2385ae HEAD@{18}: rebase (finish): returning to refs/heads/main
e2385ae HEAD@{19}: rebase (pick): Unwanted commit
692f0c0 HEAD@{20}: rebase (start): checkout HEAD~2
35ef26f HEAD@{21}: commit: Unwanted commit
bc6e197 HEAD@{22}: rebase (finish): returning to refs/heads/main
bc6e197 HEAD@{23}: rebase (squash): Created third and fourth files
e2a0e36 HEAD@{24}: rebase (start): checkout HEAD~2
8a3c3a4 HEAD@{25}: commit: chore: Added test4.md file
e2a0e36 HEAD@{26}: commit: chore: Added test3.md file
692f0c0 HEAD@{27}: commit: chore: Added test2.md file
fe53acf HEAD@{28}: reset: moving to HEAD~1
9e5058b HEAD@{29}: rebase (finish): returning to refs/heads/main
9e5058b HEAD@{30}: rebase (squash): Create a squash of two commits
723f260 HEAD@{31}: rebase (start): checkout HEAD~2
80568e9 HEAD@{32}: rebase (finish): returning to refs/heads/main
80568e9 HEAD@{33}: rebase (start): checkout HEAD~2
80568e9 HEAD@{34}: rebase (finish): returning to refs/heads/main
80568e9 HEAD@{35}: rebase (pick): chore: Created fourth file
723f260 HEAD@{36}: rebase (reword): chore: Create second file
06aea15 HEAD@{37}: rebase: fast-forward
fe53acf HEAD@{38}: rebase (start): checkout HEAD~2
08dce53 HEAD@{39}: commit (amend): chore: Created fourth file
8142256 HEAD@{40}: commit: chore: Create third and fourth files
06aea15 HEAD@{41}: commit: chore: Create another file
fe53acf HEAD@{42}: commit (initial): chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git push origin main
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 4 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (12/12), 1.08 KiB | 277.00 KiB/s, done.
Total 12 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), done.
To https://github.com/VictorMugisha/git-advanced-exercises.git
 * [new branch]      main -> main

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$
```



## Part 2: Branching Basics (10 Challenges)

### Challenge 1 - Challenge 5

```bash
victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-feature)
$ touch feature.txt

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-feature)
$ git add .

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-feature)
$ git commit -m "Implemented core functionality for new feature"
[ft/new-feature d67b3ee] Implemented core functionality for new feature
 1 file changed, 2 insertions(+)
 create mode 100644 feature.txt

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-feature)
$ git checkout main
Merge branch 'ft/new-feature' into 'main'
Switched to branch 'main'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ touch readme.txt

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add readme.txt

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "Updated project readme"
[main bd3ba1a] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git branch
  ft/branch
  ft/new-feature
* main

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git merge ft/new-feature
Merge made by the 'ort' strategy.
 feature.txt | 2 ++
 1 file changed, 2 insertions(+)
 create mode 100644 feature.txt

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git branch -d ft/new-feature
Deleted branch ft/new-feature (was d67b3ee).

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git push origin main
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (8/8), 765 bytes | 382.00 KiB/s, done.
Total 8 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), completed with 1 local object.
To https://github.com/VictorMugisha/git-advanced-exercises.git
   982ce95..0857a1e  main -> main

```


## Part 2: Branching Basics (10 Challenges)

### Challenge 6 - Challenge 10
```bash
victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
4400e9f (HEAD -> main, origin/main) Updated README.md to add bash history for Part 2: Challenge 1 - 5
0857a1e Merge branch 'ft/new-feature' into 'main'
bd3ba1a Updated project readme
d67b3ee Implemented core functionality for new feature
982ce95 chore: Added README.md file
69b5e8f Implementes test5.md
877033a chore: Created fourth file
d79a89a chore: Created second file
d514fc7 chore: Created third file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git checkout -b ft/new-branch-from-commit bd3ba1a
Switched to a new branch 'ft/new-branch-from-commit'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-branch-from-commit)
$ git log --oneline
bd3ba1a (HEAD -> ft/new-branch-from-commit) Updated project readme
982ce95 chore: Added README.md file
69b5e8f Implementes test5.md
877033a chore: Created fourth file
d79a89a chore: Created second file
d514fc7 chore: Created third file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-branch-from-commit)
$ git add .

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-branch-from-commit)
$ git commit -m "Added some files in 'ft/new-branch-from-commit' branch"
[ft/new-branch-from-commit 94deea9] Added some files in 'ft/new-branch-from-commit' branch
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-branch-from-commit)
$ git push origin ft/new-branch-from-commit
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 351 bytes | 175.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/new-branch-from-commit' on GitHub by visiting:
remote:      https://github.com/VictorMugisha/git-advanced-exercises/pull/new/ft/new-branch-from-commit
remote:
To https://github.com/VictorMugisha/git-advanced-exercises.git
 * [new branch]      ft/new-branch-from-commit -> ft/new-branch-from-commit

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-branch-from-commit)
$ git checkout main
Switched to branch 'main'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git merge ft/new-branch-from-commit
Auto-merging feature.txt
CONFLICT (add/add): Merge conflict in feature.txt
Automatic merge failed; fix conflicts and then commit the result.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main|MERGING)
$ git add feature.txt

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main|MERGING)
$ git reset
Unstaged changes after reset:
M       feature.txt

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add feature.txt

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "Reolved conflict from merging""
> ^C

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "Reolved conflict from merging"
[main a9d0638] Reolved conflict from merging
 1 file changed, 4 insertions(+), 1 deletion(-)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 384 bytes | 384.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/VictorMugisha/git-advanced-exercises.git
   4400e9f..a9d0638  main -> main

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git merge --continue
fatal: There is no merge in progress (MERGE_HEAD missing).

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git pull origin main
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 2), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), 1.87 KiB | 83.00 KiB/s, done.
From https://github.com/VictorMugisha/git-advanced-exercises
 * branch            main       -> FETCH_HEAD
   a9d0638..c947be1  main       -> origin/main
Updating a9d0638..c947be1
Fast-forward
 feature.txt | 6 +++---
 1 file changed, 3 insertions(+), 3 deletions(-)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-branch-from-commit)
$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/new-branch-from-commit)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/improved-branch-name)
$ git log --oneline
c947be1 (HEAD -> ft/improved-branch-name, origin/main, main) Merge pull request #1 from VictorMugisha/ft/new-branch-from-commit
0b618bc Merge branch 'main' into ft/new-branch-from-commit
a9d0638 Reolved conflict from merging
94deea9 (origin/ft/new-branch-from-commit) Added some files in 'ft/new-branch-from-commit' branch
4400e9f Updated README.md to add bash history for Part 2: Challenge 1 - 5
0857a1e Merge branch 'ft/new-feature' into 'main'
bd3ba1a Updated project readme
d67b3ee Implemented core functionality for new feature
982ce95 chore: Added README.md file
69b5e8f Implementes test5.md
877033a chore: Created fourth file
d79a89a chore: Created second file
d514fc7 chore: Created third file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/improved-branch-name)
$ git checkout bd3ba1a
Note: switching to 'bd3ba1a'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at bd3ba1a Updated project readme

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises ((bd3ba1a...))
$ git log --oneline
bd3ba1a (HEAD) Updated project readme
982ce95 chore: Added README.md file
69b5e8f Implementes test5.md
877033a chore: Created fourth file
d79a89a chore: Created second file
d514fc7 chore: Created third file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises ((bd3ba1a...))
$ git reset --hard bd3ba1a
HEAD is now at bd3ba1a Updated project readme

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises ((bd3ba1a...))
$ git branch
* (HEAD detached at bd3ba1a)
  ft/branch
  ft/improved-branch-name
  main

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises ((bd3ba1a...))
$ git checkout ft/branch
Previous HEAD position was bd3ba1a Updated project readme
Switched to branch 'ft/branch'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ git reset --hard ft/improved-branch-name
HEAD is now at c947be1 Merge pull request #1 from VictorMugisha/ft/new-branch-from-commit

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ git checkout ft/improved-branch-name
Switched to branch 'ft/improved-branch-name'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/improved-branch-name)
$ git push origin ft/improved-branch-name
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'ft/improved-branch-name' on GitHub by visiting:
remote:      https://github.com/VictorMugisha/git-advanced-exercises/pull/new/ft/improved-branch-name
remote:
To https://github.com/VictorMugisha/git-advanced-exercises.git
 * [new branch]      ft/improved-branch-name -> ft/improved-branch-name
```

## Part 3: Advanced Workflow

### Challenge 1 - Challenge 5


```bash
victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test1.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git stash
Saved working directory and index state WIP on main: 904fd16 Updated README.md to add bash history of part 2 challenge 6 - 
10

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git stash
Saved working directory and index state WIP on main: 904fd16 Updated README.md to add bash history of part 2 challenge 6 - 
10

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git stash list
stash@{0}: WIP on main: 904fd16 Updated README.md to add bash history of part 2 challenge 6 - 10
stash@{1}: WIP on main: 904fd16 Updated README.md to add bash history of part 2 challenge 6 - 10

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git stash pop
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test1.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (981559726f8414024c8dd848979c102b3b83f7af)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git stash list
stash@{0}: WIP on main: 904fd16 Updated README.md to add bash history of part 2 challenge 6 - 10

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git stash
Saved working directory and index state WIP on main: 904fd16 Updated README.md to add bash history of part 2 challenge 6 - 
10

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git stash list
stash@{0}: WIP on main: 904fd16 Updated README.md to add bash history of part 2 challenge 6 - 10
stash@{1}: WIP on main: 904fd16 Updated README.md to add bash history of part 2 challenge 6 - 10

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git stash apply
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test1.md

no changes added to commit (use "git add" and/or "git commit -a")

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git stash list
stash@{0}: WIP on main: 904fd16 Updated README.md to add bash history of part 2 challenge 6 - 10
stash@{1}: WIP on main: 904fd16 Updated README.md to add bash history of part 2 challenge 6 - 10

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git stash pop
error: Your local changes to the following files would be overwritten by merge:
        test1.md
Please commit your changes or stash them before you merge.
Aborting
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test1.md

no changes added to commit (use "git add" and/or "git commit -a")
The stash entry is kept in case you need it again.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add test1.md

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "Playing around with stashing"
[main 3d4be8c] Playing around with stashing
 1 file changed, 5 insertions(+)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git checkout ft/branch
Switched to branch 'ft/branch'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ git add .

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ git commit -m "Made changes in ft/branch branch"
[ft/branch a80ad3d] Made changes in ft/branch branch
 1 file changed, 3 insertions(+)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (ft/branch)
$ git checkout main
Switched to branch 'main'

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add .

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "Made same chanes from main"
[main 02f9de1] Made same chanes from main
 1 file changed, 1 insertion(+), 3 deletions(-)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git merge ft/branch
Auto-merging test1.md
CONFLICT (content): Merge conflict in test1.md
Automatic merge failed; fix conflicts and then commit the result.

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main|MERGING)
$ git add .

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main|MERGING)
$ git commit -m "Resolved conflict"
[main bce6761] Resolved conflict

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git merge --continue
fatal: There is no merge in progress (MERGE_HEAD missing).

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$
```


## Part 3: Advanced Workflow

### Challenge 6 - Challenge 10

```bash
victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git tag v1.0

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git tag
v1.0

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git push origin v1.0
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/VictorMugisha/git-advanced-exercises.git
 * [new tag]         v1.0 -> v1.0

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git tag -d v1.0
Deleted tag 'v1.0' (was 7672a51)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git add .gitignore

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git commit -m "Added a .gitignore file"
[main dbdd728] Added a .gitignore file
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 295 bytes | 295.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/VictorMugisha/git-advanced-exercises.git
   7672a51..dbdd728  main -> main

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git status
On branch main
nothing to commit, working tree clean

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git pull origin main
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 991 bytes | 45.00 KiB/s, done.
From https://github.com/VictorMugisha/git-advanced-exercises
 * branch            main       -> FETCH_HEAD
   dbdd728..5279b79  main       -> origin/main
Updating dbdd728..5279b79
Fast-forward
 test1.md | 2 ++
 1 file changed, 2 insertions(+)

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$ git log --oneline
5279b79 (HEAD -> main, origin/main) Update test1.md from remote branch on GitHub
dbdd728 Added a .gitignore file
7672a51 Added bash history for Part 3 Challenge 1 - 5
bce6761 Resolved conflict
02f9de1 Made same chanes from main
a80ad3d (ft/branch) Made changes in ft/branch branch
3d4be8c Playing around with stashing
904fd16 Updated README.md to add bash history of part 2 challenge 6 - 10
c947be1 (origin/ft/improved-branch-name, ft/improved-branch-name) Merge pull request #1 from VictorMugisha/ft/new-branch-from-commit
0b618bc Merge branch 'main' into ft/new-branch-from-commit
a9d0638 Reolved conflict from merging
94deea9 (origin/ft/new-branch-from-commit) Added some files in 'ft/new-branch-from-commit' branch
4400e9f Updated README.md to add bash history for Part 2: Challenge 1 - 5
0857a1e Merge branch 'ft/new-feature' into 'main'
bd3ba1a Updated project readme
d67b3ee Implemented core functionality for new feature
982ce95 chore: Added README.md file
69b5e8f Implementes test5.md
877033a chore: Created fourth file
d79a89a chore: Created second file
d514fc7 chore: Created third file
fe53acf chore: Create initial file

victo@DESKTOP-VEQ8F6B MINGW64 ~/OneDrive/Documents/git_learning/advancedExercises (main)
$
```