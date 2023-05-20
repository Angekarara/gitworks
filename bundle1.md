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