<!-- Project initialization -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git init
Initialized empty Git repository in /home/ivy/Development/ojemba/git/gym-git-exercise-solution/.git/

<!-- Branch main creation and switching -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git branch
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b main
Switched to a new branch 'main'

<!-- Staging changes made to readme file and committing them -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Add first terminal history in readme file"
[main (root-commit) 64c6f41] Add first terminal history in readme file
 1 file changed, 7 insertions(+)
 create mode 100644 README.md

 <!-- Connecting remote repo to local project -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git remote add origin git@github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git

<!-- Pushing local changes into the main branch in remote repo -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 414 bytes | 414.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.

<!-- Create a dev branch and switch to it -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b dev
Switched to a new branch 'dev'

<!-- Create a test branch and switch to it -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b test
Switched to a new branch 'test'

<!-- Switch back to dev branch -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout dev
M       README.md
Switched to branch 'dev'

<!-- Check all the created branches -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git branch -a
* dev
  main
  test
  remotes/origin/main

  <!-- Delete test branch -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git branch --delete test
Deleted branch test (was 64c6f41).

<!-- List the remaining branches -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git branch -a
* dev
  main
  remotes/origin/main

<!-- Create home page stage changes and stash the changes -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch home.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash save "temporily save changes in home page file"
Saved working directory and index state On dev: temporily save changes in home page file

<!-- Create about page stage changes and stash the changes -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch about.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash save "Temporily save changes in the about page file"
Saved working directory and index state On dev: Temporily save changes in the about page file

<!-- Create team page stage changes and stash the changes -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch team.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash save "temporily save changes in team page file"
Saved working directory and index state On dev: temporily save changes in team page file

<!-- List all the stashed files -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash list
stash@{0}: On dev: temporily save changes in team page file
stash@{1}: On dev: Temporily save changes in the about page file
stash@{2}: On dev: temporily save changes in home page file

<!-- stash pop to restore changes in about page -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash pop stash@{1}
On branch dev
Your branch is up to date with 'origin/dev'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Dropped stash@{1} (7da920374bb642cdd4f35de4f18b3392204003fc)

<!-- List the remaining stashes -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash list
stash@{0}: On dev: temporily save changes in team page file
stash@{1}: On dev: temporily save changes in home page file

<!-- used stash apply but encountered a conflicting due to merge conflict in readme a-->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash apply stash@{1}
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch dev
Your branch is ahead of 'origin/dev' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html

Unmerged paths:
  (use "git restore --staged <file>..." to unstage)
  (use "git add <file>..." to mark resolution)
        both modified:   README.md
<!-- Staged changes in home page file commited and pushed them  -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "make changes to readme file"
[dev 3c36d78] make changes to readme file
 2 files changed, 13 insertions(+), 1 deletion(-)
 create mode 100644 home.html
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git status
On branch dev
Your branch is ahead of 'origin/dev' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 8 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (8/8), 1.34 KiB | 457.00 KiB/s, done.
Total 8 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   c49ac11..3c36d78  dev -> dev

<!-- Created an new file and used git stash pop --index to bring unstash worked successfully -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash list
stash@{0}: On dev: save new home page
stash@{1}: On dev: temporily save changes in team page file
stash@{2}: On dev: temporily save changes in home page file
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git stash pop --index stash@{0}
Removing home.thml
On branch dev
Your branch is up to date with 'origin/dev'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html
        deleted:    home.thml

Dropped stash@{0} (0209a14f16c243293329822b4ba7b50957f42c2b)

<!-- Staged changes committed and pushed them -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "rename home page and stash pop"
[dev 1958d9f] rename home page and stash pop
 2 files changed, 12 insertions(+)
 create mode 100644 home.html
 delete mode 100644 home.thml
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 472 bytes | 472.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
   1560aa2..1958d9f  dev -> dev

<!-- Create an ft/bundle-2 branch and create a services page -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout -b ft/bundle-2
Switched to a new branch 'ft/bundle-2'
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ touch services.html

<!-- Stage the changes and commit them -->
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git add .
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git commit -m "Create a service page"
[ft/bundle-2 815d283] Create a service page
 2 files changed, 3 insertions(+), 1 deletion(-)
 create mode 100644 services.html


<!-- Push the chnages to the github repo -->
 ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git push -u origin ft/bundle-2
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 463 bytes | 463.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting:
remote:      https://github.com/Murage-Ivy/Gym-Git-Exercise-Solutions/pull/new/ft/bundle-2
remote: 
To github.com:Murage-Ivy/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/bundle-2 -> ft/bundle-2
Branch 'ft/bundle-2' set up to track remote branch 'ft/bundle-2' from 'origin'.

```
## Checkout your main branch and pull the latest changes
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git fetch
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 628 bytes | 628.00 KiB/s, done.
From github.com:Murage-Ivy/Gym-Git-Exercise-Solutions
   64c6f41..cd99c3d  main       -> origin/main
ivy@ivy-HP-ProBook-430-G7:~/Development/ojemba/git/gym-git-exercise-solution$ git pull 
Updating 64c6f41..cd99c3d
Fast-forward
 README.md     | 207 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++--
 about.html    |  12 ++++++++
 home.html     |  12 ++++++++
 services.html |   0
 team.html     |  12 ++++++++
 5 files changed, 241 insertions(+), 2 deletions(-)
 create mode 100644 about.html
 create mode 100644 home.html
 create mode 100644 services.html
 create mode 100644 team.html