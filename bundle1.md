angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git status
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        home.html

nothing added to commit but untracked files present (use "git add" to track)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git add .

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git status
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html


angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash save "saving current changes" 
Saved working directory and index state On dev: saving current changes

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git status
On branch dev
nothing to commit, working tree clean

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash list
stash@{0}: On dev: saving current changes

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ touch about.html

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git status
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        about.html

nothing added to commit but untracked files present (use "git add" to track)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git add .

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash save "about file"
Saved working directory and index state On dev: about file

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ touch team.html

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git add .

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash save "team file"
Saved working directory and index state On dev: team file

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash list
stash@{0}: On dev: team file
stash@{1}: On dev: about file
stash@{2}: On dev: saving current changes

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash pop stash@{2}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html

Dropped stash@{2} (c1ec857e20eaf34782cfa5756077171cf1f7e06f)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash save "home file"
Saved working directory and index state On dev: home file

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash list
stash@{0}: On dev: home file
stash@{1}: On dev: team file
stash@{2}: On dev: about file

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash pop stash@{1}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

Dropped stash@{1} (8b60426499d968b5cb2cec3165fabfa2c688ea4f)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash pop stash@{2}
fatal: log for 'stash' only has 2 entries

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash list
stash@{0}: On dev: home file
stash@{1}: On dev: about file

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash pop stash@{0}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html
        new file:   team.html

Dropped stash@{0} (349952be59248b032d48dda68e45c524f0172a89)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git status
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html
        new file:   team.html


angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git commit -m "my files"
[dev 74411bc] my files
 2 files changed, 12 insertions(+)
 create mode 100644 home.html
 create mode 100644 team.html

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git push origin dev
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 523 bytes | 13.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'dev' on GitHub by visiting:
remote:      https://github.com/Angekarara/gitworks/pull/new/dev
remote:
To https://github.com/Angekarara/gitworks.git
 * [new branch]      dev -> dev

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash list
stash@{0}: On dev: about file

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git stash pop stash@{0}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Dropped stash@{0} (38f36e5375c429cbec8b376eec8fca0a4c48e01d)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git reset about.html

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$ git status
On branch dev
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        about.html

nothing added to commit but untracked files present (use "git add" to track)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (dev)
$
angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/service-redesign)
$ git merge main
Auto-merging service.html
CONFLICT (content): Merge conflict in service.html
Automatic merge failed; fix conflicts and then commit the result.

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/service-redesign|MERGING)
$ git status
On branch ft/service-redesign
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   service.html

no changes added to commit (use "git add" and/or "git commit -a")

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/service-redesign|MERGING)
$ git add .

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/service-redesign|MERGING)
$ git commit -m "third commit"
[ft/service-redesign a7b885e] third commit

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/service-redesign)
$ git push origin ft/service-redesign 
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 360 bytes | 120.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Angekarara/gitworks.git
   f92b351..a7b885e  ft/service-redesign -> ft/service-redesign

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/service-redesign)
$ git checkout -b ft/team-page
Switched to a new branch 'ft/team-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ touch team.html

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git add .

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git push origin ft/team-page 
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'ft/team-page' on GitHub by visiting:
remote:      https://github.com/Angekarara/gitworks/pull/new/ft/team-page
remote:
To https://github.com/Angekarara/gitworks.git
 * [new branch]      ft/team-page -> ft/team-page

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git checkout main
Switched to branch 'main'
D       bundle1.md
A       bundles.md

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git checkout -b ft/contact-page
Switched to a new branch 'ft/contact-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git checkout ft/team-page
Switched to branch 'ft/team-page'
D       bundle1.md
A       bundles.md

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git log
commit a7b885ebffa9d54d6bb9e0a05fce181ae076283d (HEAD -> ft/team-page, origin/ft/team-page, origin/ft/service-redesign, ft/service-redesign)
commit a7b885ebffa9d54d6bb9e0a05fce181ae076283d (HEAD -> ft/team-page, origin/ft/team-page, origin/ft/service-redesign, ft/service-redesign)
commit a7b885ebffa9d54d6bb9e0a05fce181ae076283d (HEAD -> ft/team-page, origin/ft/team-page, origin/ft/service-redesign, ft/service-redesign)
Merge: f92b351 7e6e9a9
Author: Angekarara <mbabange2020@gmail.com>
Date:   Sat May 20 17:13:33 2023 +0200

    third commit

commit 7e6e9a9ca3cbac26b78c10bdd69b37e9a39c4804 (origin/main, main, ft/contact-page)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git status
On branch ft/contact-page
nothing to commit, working tree clean

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git branch
  dev
  ft/bundle-2
* ft/contact-page
  ft/service-redesign
  ft/team-page
  main

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git log
commit ffe21de6819e30ea63312b14ffe6d39d67596fb1 (HEAD -> ft/contact-page)
commit ffe21de6819e30ea63312b14ffe6d39d67596fb1 (HEAD -> ft/contact-page)
commit ffe21de6819e30ea63312b14ffe6d39d67596fb1 (HEAD -> ft/contact-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Sat May 20 17:51:30 2023 +0200

    commit on bundles

commit 7e6e9a9ca3cbac26b78c10bdd69b37e9a39c4804 (origin/main, main)
Author: Angekarara <mbabange2020@gmail.com>

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git branch
  dev
  ft/bundle-2
* ft/contact-page
  ft/service-redesign
  ft/team-page
  main

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git checkout ft/team-page 
Switched to branch 'ft/team-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git lo
git: 'lo' is not a git command. See 'git --help'.

The most similar commands are
        log
        flow

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git log
commit a7b885ebffa9d54d6bb9e0a05fce181ae076283d (HEAD -> ft/team-page, origin/ft/team-page, origin/ft/service-redesign, ft/service-redesign)
Merge: f92b351 7e6e9a9
commit a7b885ebffa9d54d6bb9e0a05fce181ae076283d (HEAD -> ft/team-page, origin/ft/team-page, origin/ft/service-redesign, ft/service-redesign)
Merge: f92b351 7e6e9a9
Author: Angekarara <mbabange2020@gmail.com>
Date:   Sat May 20 17:13:33 2023 +0200

    third commit

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git log
commit a7b885ebffa9d54d6bb9e0a05fce181ae076283d (HEAD -> ft/team-page, origin/ft/team-page, origin/ft/service-redesign, ft/service-redesign)
Merge: f92b351 7e6e9a9
commit a7b885ebffa9d54d6bb9e0a05fce181ae076283d (HEAD -> ft/team-page, origin/ft/team-page, origin/ft/service-redesign, ft/service-redesign)
Merge: f92b351 7e6e9a9
Author: Angekarara <mbabange2020@gmail.com>
Date:   Sat May 20 17:13:33 2023 +0200

    third commit

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git branch -d ft/team-page 
error: Cannot delete branch 'ft/team-page' checked out at 'C:/Users/angek/Desktop/CSSFlex'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git checkout main 
Switched to branch 'main'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git branch -d ft/team-page
error: The branch 'ft/team-page' is not fully merged.
If you are sure you want to delete it, run 'git branch -D ft/team-page'.

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git branch -D ft/team-page
Deleted branch ft/team-page (was a7b885e).

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git pull origin  main 
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 629 bytes | 10.00 KiB/s, done.
From https://github.com/Angekarara/gitworks
 * branch            main       -> FETCH_HEAD
   7e6e9a9..69ede71  main       -> origin/main
Updating 7e6e9a9..69ede71
Fast-forward
 service.html | 4 ++++
 1 file changed, 4 insertions(+)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git log
commit 69ede71ca1cc784e18382691b3981a0d906592ee (HEAD -> main, origin/main)
Merge: 7e6e9a9 a7b885e
Author: Angekarara <99403587+Angekarara@users.noreply.github.com>
Date:   Sat May 20 18:01:47 2023 +0200

    Merge pull request #3 from Angekarara/ft/service-redesign

    Ft/service redesign

commit a7b885ebffa9d54d6bb9e0a05fce181ae076283d (origin/ft/team-page, origin/ft/service-redesign, ft/service-redesign)
Merge: f92b351 7e6e9a9
Author: Angekarara <mbabange2020@gmail.com>
Date:   Sat May 20 17:13:33 2023 +0200

    third commit

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git checkout -b ft/team-page
Switched to a new branch 'ft/team-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git status
On branch ft/team-page
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   team.html

no changes added to commit (use "git add" and/or "git commit -a")

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git add .

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git commit -m "commit on team"
[ft/team-page 6a63193] commit on team
 1 file changed, 12 insertions(+)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git push origin ft/team-page 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 430 bytes | 71.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Angekarara/gitworks.git
   a7b885e..6a63193  ft/team-page -> ft/team-page

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git checkout main 
Switched to branch 'main'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git checkout -b ft/contact-page
fatal: a branch named 'ft/contact-page' already exists

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git branch -D ft/contact-page 
Deleted branch ft/contact-page (was ffe21de).

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git checkout -b ft/contact-page
Switched to a new branch 'ft/contact-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git checkout ft/team-page 
Switched to branch 'ft/team-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git log
commit 6a631930b184fe827b975fcd4092038fff9b7012 (HEAD -> ft/team-page, origin/ft/team-page)
Author: Angekarara <mbabange2020@gmail.com>
Date:   Sat May 20 18:04:56 2023 +0200

    commit on team

commit 69ede71ca1cc784e18382691b3981a0d906592ee (origin/main, main, ft/contact-page)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git checkout ft/contact-page 
Switched to branch 'ft/contact-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git cherry-pick 6a631930b184fe827b975fcd4092038fff9b70121
fatal: bad revision '6a631930b184fe827b975fcd4092038fff9b70121'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git log
commit 69ede71ca1cc784e18382691b3981a0d906592ee (HEAD -> ft/contact-page, origin/main, main)
Merge: 7e6e9a9 a7b885e
Author: Angekarara <99403587+Angekarara@users.noreply.github.com>
Date:   Sat May 20 18:01:47 2023 +0200

    Merge pull request #3 from Angekarara/ft/service-redesign

    Ft/service redesign

commit a7b885ebffa9d54d6bb9e0a05fce181ae076283d (origin/ft/service-redesign, ft/service-redesign)
Merge: f92b351 7e6e9a9
Author: Angekarara <mbabange2020@gmail.com>
Date:   Sat May 20 17:13:33 2023 +0200
commit 69ede71ca1cc784e18382691b3981a0d906592ee (HEAD -> ft/contact-page, origin/main, main)
Merge: 7e6e9a9 a7b885e
Author: Angekarara <99403587+Angekarara@users.noreply.github.com>
Date:   Sat May 20 18:01:47 2023 +0200

    Merge pull request #3 from Angekarara/ft/service-redesign

    Ft/service redesign


angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git cherry-pick 6a631930b184fe827b975fcd4092038fff9b70121
fatal: bad revision '6a631930b184fe827b975fcd4092038fff9b70121'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git cherry-pick 6a63193
The previous cherry-pick is now empty, possibly due to conflict resolution.
If you wish to commit it anyway, use:

    git commit --allow-empty

Otherwise, please use 'git cherry-pick --skip'
On branch ft/team-page
You are currently cherry-picking commit 6a63193.
  (all conflicts fixed: run "git cherry-pick --continue")
  (use "git cherry-pick --skip" to skip this patch)
  (use "git cherry-pick --abort" to cancel the cherry-pick operation)

nothing to commit, working tree clean

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page|CHERRY-PICKING)
$ git checkout ft/contact-page 
Switched to branch 'ft/contact-page'
warning: cancelling a cherry picking in progress

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git cherry-pick 6a63193
[ft/contact-page 2c89d72] commit on team
 Date: Sat May 20 18:04:56 2023 +0200
 1 file changed, 12 insertions(+)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git checkout ft/team-page 
Switched to branch 'ft/team-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git log --oneline
6a63193 (HEAD -> ft/team-page, origin/ft/team-page) commit on team
69ede71 (origin/main, main) Merge pull request #3 from Angekarara/ft/service-redesign
a7b885e (origin/ft/service-redesign, ft/service-redesign) third commit
7e6e9a9 commit on service
f92b351 second commit on service
631a75f Merge pull request #1 from Angekarara/ft/bundle-2
357c4ff (origin/ft/bundle-2, ft/bundle-2) bundle 2

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git add .

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git commit -m "comit on team page"
On branch ft/team-page
nothing to commit, working tree clean

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git push origin ft/team-page 
Everything up-to-date

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ ls
about.html  bundle1.md  home.html  index.html  service.html  style.css  team.html

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git checkout ft/contact-page 
Switched to branch 'ft/contact-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git branch
  dev
  ft/bundle-2
* ft/contact-page
  ft/service-redesign
  ft/team-page
  main

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git pull origin ft/contact-page
fatal: couldn't find remote ref ft/contact-page

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/contact-page)
$ git checkout -b ft/faq-page
Switched to a new branch 'ft/faq-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/faq-page)
$ touch faq.html

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/faq-page)
$ git add .

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/faq-page)
$ git commit -m "faq commit"
[ft/faq-page 44800fd] faq commit
 1 file changed, 12 insertions(+)
 create mode 100644 faq.html

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/faq-page)
$ git push origin ft/faq-page 
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 678 bytes | 30.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Angekarara/gitworks/pull/new/ft/faq-page
remote:
To https://github.com/Angekarara/gitworks.git
 * [new branch]      ft/faq-page -> ft/faq-page

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/faq-page)
$ git checkout ft/team-page
Switched to branch 'ft/team-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git revert 6a63193
hint: Waiting for your editor to close the file... Vim: Error reading input, exiting...
Vim: Finished.

error: There was a problem with the editor 'vi'.
Please supply the message using either -m or -F option.

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git revert 6a63193
error: your local changes would be overwritten by revert.
hint: commit your changes or stash them to proceed.
fatal: revert failed

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git commit -m "commit"
[ft/team-page 76ac07d] commit
 1 file changed, 12 deletions(-)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git revert 6a63193
On branch ft/team-page
nothing to commit, working tree clean

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git push origin ft/team-page 
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 217 bytes | 108.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Angekarara/gitworks.git
   6a63193..76ac07d  ft/team-page -> ft/team-page

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/team-page)
$ git checkout ft/faq-page 
Switched to branch 'ft/faq-page'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/faq-page)
$ git checkout -b ft/home-page-redesign
Switched to a new branch 'ft/home-page-redesign'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/home-page-redesign)
$ git checkout main
Switched to branch 'main'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   home.html

no changes added to commit (use "git add" and/or "git commit -a")

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git add .

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git commit -m "gg"
[main ae6f740] gg
 1 file changed, 1 insertion(+), 1 deletion(-)

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git push origin main 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 291 bytes | 48.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Angekarara/gitworks.git
   69ede71..ae6f740  main -> main

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (main)
$ git checkout ft/home-page-redesign
Switched to branch 'ft/home-page-redesign'

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/home-page-redesign)
$ git fetch

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/home-page-redesign)
$ git rebase main
Successfully rebased and updated refs/heads/ft/home-page-redesign.

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/home-page-redesign)
$ git add .

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/home-page-redesign)
$ git commit -m "ft/home-pagre-redesign"
On branch ft/home-page-redesign
nothing to commit, working tree clean

angek@DESKTOP-VBK91UM MINGW64 ~/Desktop/CSSFlex (ft/home-page-redesign)
$ git push origin ft/home-page-redesign 
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 681 bytes | 48.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/Angekarara/gitworks/pull/new/ft/home-page-redesign
remote:
To https://github.com/Angekarara/gitworks.git
 * [new branch]      ft/home-page-redesign -> ft/home-page-redesign